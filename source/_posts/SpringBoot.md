---
title: SpringBoot
date: 2020-07-16
categories:
  - Spring
author: 胡先森
---

SpringBoot 是基于 SpringFramework 的企业级应用开发框架，有了 SpringFramework 的基础，相信理解 SpringBoot 并不是一件难事。

<!-- more -->

# SpringBoot 启动原理

## @SpringBootApplication

在 SpringBoot 项目中，一般情况下都有且仅有一个启动类：

```java
@SpringBootApplication
public class Application {
    public static void main(String[] args) {
        SpringApplication.run(Application.class, args);
    }
}
```

其中@SpringBootApplication 注解是 SpringBoot 的核心注解，它其实是一个组合注解：

```java
@Target(ElementType.TYPE)
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Inherited
@SpringBootConfiguration
@EnableAutoConfiguration
@ComponentScan(excludeFilters = {
		@Filter(type = FilterType.CUSTOM, classes = TypeExcludeFilter.class),
		@Filter(type = FilterType.CUSTOM, classes = AutoConfigurationExcludeFilter.class) })
public @interface SpringBootApplication {
    // ....
}
```

其中重要的有三个 Annotation：

1. @Configuration（@SpringBootConfiguration 也是应用了@Configuration）
2. @EnableAutoConfiguration
3. @ComponentScan

即 SpringBoot 项目的启动类也可以这么写（优化 SpringBoot 项目的启动时间就可以将注解拆开来写，缩小包扫描的范围）：

```java
@Configuration
@EnableAutoConfiguration
@ComponentScan
public class Application {
    public static void main(String[] args) {
        SpringApplication.run(Application.class, args);
    }
}
```

## 注解解析

### @Configuration

这里的@Configuration 与 JavaConfig 形式的 Spring IoC 容器的配置类使用的@Configuration 注解作用相同，启动类加上这个注解之后，本身就变成了 IoC 容器的配置类。

@Configuration 的注解类标识这个类可以使用 Spring IoC 容器作为 Bean 定义的来源。@Bean 注解告诉 Spring，一个带有@Bean 的注解方法将返回一个对象，该对象应该被注册为在 Spring 应用程序上下文中的 Bean。

### @ComponentScan

@ComponentScan 的功能是自动扫描并加载符合条件的组件（比如@Component 和@Repository 以及其他衍生注解）或者 Bean 定义，最终将这些 Bean 定义加载到 IoC 容器当中。

可以通过@ComponentScan 的一些属性来进行细粒度的定制自动扫描的范围，如果不指定，Spring 框架实现默认会从启动类所在的类的包进行扫描，所以启动类最好是放在所有的业务代码的外层，但如果要放在根目录（com 包）下需要谨慎，低版本的 SpringBoot 会有一些兼容性的问题。

### @EnableAutoConfiguration

@EnableAutoConfiguration 借助@Import 的支持，收集和注册特定场景相关的 Bean 定义，在 SpringBoot 中还有一些与之类似的注解：

- @EnableScheduling 是通过@Import 将 Spring 调度框架相关的 Bean 定义都加载到 IoC 容器
- @EnableMBeanExport 是通过@Import 将 JMX 相关的 Bean 定义加载到 IoC 容器
- @EnableCaching 是通过@Impotr 将将缓存相关的 Bean 定义加载到 IoC 容器

@EnableAutoConfiguration 也是通过@Import 将所有符合自动装配条件的 Bean 定义加载到 IoC 容器，会根据类路径中的 jar 依赖为项目进行自动配置，如：添加了 spring-boot-starter-web 依赖，会自动添加 Tomcat 和 Spring MVC 的依赖，SpringBoot 会对 Tomcat 和 Spring MVC 进行自动配置。

@EnableAutoConfiguration 作为一个组合注解，其自身定义关键信息如下：

```java
@SuppressWarnings("deprecation")
@Target(ElementType.TYPE)
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Inherited
@AutoConfigurationPackage
@Import(AutoConfigurationImportSelector.class)
public @interface EnableAutoConfiguration {
    // ...
}
```

借助 AutoConfigurationImportSelector，SpringBoot 可以将所有符合条件的@Configuration 配置都加载到当前 SpringBoot 创建并使用的 IoC 容器，借助 Spring 框架的一个工具类 SpringFactoriesLoader，@EnableAutoConfiguration 可以智能的完成自动配置的功能。

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6mychickmupWyfMiax0ryO6Hs4SYOv1IzQzmAj46icFN8ATeAbRhibHNmvNLt8zniczDnVPEIvBHEDSv8WZ38hoSkXg/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

在这其中，SpringFactoriesLoader 扮演者十分重要的角色：

```java
public abstract class SpringFactoriesLoader {
    //...
    public static <T> List<T> loadFactories(Class<T> factoryClass, ClassLoader classLoader) {
        ...
    }


    public static List<String> loadFactoryNames(Class<?> factoryClass, ClassLoader classLoader) {
        ....
    }
}
```

配合@EnableAutoConfiguration 使用的话，它更多提供了一种配置查找的功能支持，即根据@EnableAutoConfiguration 的完整类名 org.springframework.boot.autoconfigure.EnableAutoConfiguration 作为查找 key，获取对应一组的@Configure 类。

总的来说，@EnaleAutoConfiguration 的作用是从 classpath 中搜寻所有的 META-INF/spring.factories 配置文件，并将其中 org.springframework.boot.autoconfigure.EnableAutoConfiguration 对应的配置项，通过反射实例化为标注了@Configuration 的 JavaConfig 形式的 IoC 容器配置类，然后加载到 IoC 容器当中。

## 启动执行流程

### 流程概览

1. 使用 SpringApplication 的静态的 run 方法，而这个静态的 run 方法最终会调用 SpringApplication 实例的 run 方法，因此首先需要创建一个 SpringApplication 对象实例，然后调用这个创建号的 SpringApplication 的实例方法，在 SpringApplication 实例初始化的时候，它会提前做几件事情：
   - 根据 classpath 里面是否存在某个特征类 org.springframework.boot.ConfigurableWebApplicationContext 来决定是否应该创建一个 Web 应用使用的 ApplicationContext 类型
   - 使用 SpringFactoriesLoader 在应用的 classpath 中查找并加载所有可能的 ApplicationContextInitializer
   - 使用 SpringFactories 在应用的 classpath 中查找并加载所有可能的 ApplicationListener
   - 推断并设置 main 方法的定义类
2. SpringApplication 实例初始化完成并且完成设置后，就可以开始执行 run 方法的逻辑了，首先遍历执行所有通过 SpringFactories 可以查找到并加载的 SpringApplicationRunListener，调用他们的 started()方法
3. 创建并配置当前 SpringBoot 应用将要使用的 Environment（包括要使用的 PropertySource 以及 Profile）、
4. 调用所有的 SpringApplicationRunListener 的 environmentPrepared()的方法
5. 如果 SpringApplication 的 showBanner 属性被设置为 true，则打印 banner
6. 根据用户是否明确设置了 applicationContextClass 类型以及初始化阶段的推断结果，决定该为当前 SpringBoot 应用创建什么类型的 ApplicationContext 并创建完成，然后根据条件决定是否添加 ShutdownHook，决定是否使用自定义的 BeanNameGenerator，决定是否使用自定义的 ResourceLoader，并且将之前准备好的 Environment 设置给创建好的 ApplicationContext 使用
7. ApplicationContext 创建好之后，SpringApplication 会再次借助 Spring-FactoriesLoader，查找并加载 classpath 中所有可用的 ApplicationContext-Initializer，然后遍历调用这些 ApplicationContextInitializer 的 initialize（applicationContext）方法来对已经创建好的 ApplicationContext 进行进一步的处理
8. 遍历所有 SpringApplicationRunListener 的 contextPrepared()方法
9. 最核心的一步，将之前通过@EnableAutoConfiguration 获取的所有配置以及其他形式的 IoC 容器配置加载到已经准备完毕的 ApplicationContext
10. 遍历调用所有 SpringApplicationRunListener 的 contextLoaded()方法
11. 调用 ApplicationContext 的 refresh()方法，完成 IoC 容器可用的最后一道工序
12. 查找当前 ApplicationContext 中是否注册有 CommandLineRunner，如果有，则遍历执行它们
13. 正常情况下，遍历执行 SpringApplicationListener 的 finished()方法（如果整个过程出现异常，则依然调用所有 SpringApplicationRunListener 的 finished()方法，只不过这种情况下会将一场信息一并传入处理

去掉事件通知点后，整体流程大体如下：

<img src="https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210624210942919.png" alt="image-20210624210942919" style="zoom:50%;" />

简单一点，也可以将启动流程分为三个部分：

1. 第一部分进行 SpringApplication 的初始化模块，配置一些基本的环境变量、资源、构造器、监听器
2. 第二部分实现了应用具体的启动方案，包括启动流程的监听模块、加载配置环境模块、及核心的创建上下文环境模块
3. 第三部分是自动化配置模块，该模块是 SpringBoot 自动配置的核心。

### 启动详情

首先进入 run 方法：

```java
	public static ConfigurableApplicationContext run(Class<?> primarySource,
			String... args) {
		return run(new Class<?>[] { primarySource }, args);
	}
```

可以看到调用了重载的 run 方法：

```java
	public static ConfigurableApplicationContext run(Class<?>[] primarySources,
			String[] args) {
		return new SpringApplication(primarySources).run(args);
	}

```

依然是一个静态方法，这里首先要构造一个 SpringApplication 实例，然后再调用实例的 run 方法，这里的构造方法也有重载的版本，最终调用的构造方法：

```java
public SpringApplication(ResourceLoader resourceLoader, Class<?>... primarySources) {
   this.resourceLoader = resourceLoader;
   Assert.notNull(primarySources, "PrimarySources must not be null");
   this.primarySources = new LinkedHashSet<>(Arrays.asList(primarySources));
   this.webApplicationType = WebApplicationType.deduceFromClasspath();
   setInitializers((Collection) getSpringFactoriesInstances(
         ApplicationContextInitializer.class));
   setListeners((Collection) getSpringFactoriesInstances(ApplicationListener.class));
   this.mainApplicationClass = deduceMainApplicationClass();
}
```

这里主要是为 SpringApplication 对象赋一些初值。构造函数执行完毕后，我们回到 run 方法:

```java
public ConfigurableApplicationContext run(String... args) {
		StopWatch stopWatch = new StopWatch();
		stopWatch.start();
		ConfigurableApplicationContext context = null;
		Collection<SpringBootExceptionReporter> exceptionReporters = new ArrayList<>();
		configureHeadlessProperty();
		SpringApplicationRunListeners listeners = getRunListeners(args);
		listeners.starting();
		try {
			ApplicationArguments applicationArguments = new DefaultApplicationArguments(
					args);
			ConfigurableEnvironment environment = prepareEnvironment(listeners,
					applicationArguments);
			configureIgnoreBeanInfo(environment);
			Banner printedBanner = printBanner(environment);
			context = createApplicationContext();
			exceptionReporters = getSpringFactoriesInstances(
					SpringBootExceptionReporter.class,
					new Class[] { ConfigurableApplicationContext.class }, context);
			prepareContext(context, environment, listeners, applicationArguments,
					printedBanner);
			refreshContext(context);
			afterRefresh(context, applicationArguments);
			stopWatch.stop();
			if (this.logStartupInfo) {
				new StartupInfoLogger(this.mainApplicationClass)
						.logStarted(getApplicationLog(), stopWatch);
			}
			listeners.started(context);
			callRunners(context, applicationArguments);
		}
		catch (Throwable ex) {
			handleRunFailure(context, ex, exceptionReporters, listeners);
			throw new IllegalStateException(ex);
		}

		try {
			listeners.running(context);
		}
		catch (Throwable ex) {
			handleRunFailure(context, ex, exceptionReporters, null);
			throw new IllegalStateException(ex);
		}
		return context;
	}
```

该方法中有几个关键步骤：

1. 创建了应用的见同期 SpringApplicationRunListeners 并开始监听

2. 加载 SpringBoot 配置环境（ConfigurableEnvironment），如果是通过 Web 容器发布，会加载 StandardEnvironment，其最终也是集成了 ConfigurableEnvironment，类图如下

   ![图片](https://mmbiz.qpic.cn/mmbiz_png/6mychickmupWyfMiax0ryO6Hs4SYOv1IzQurfYCoiaPsiaBBeBrCWOHMTHwl7mQ6iaYqKYMoRbT2bz6270LohsDndIg/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

3. 配置环境（Environment）加入到监听器对象中（SpringApplicationRunListeners）

4. 创建 run 方法的返回对象：ConfigurableApplicationContext（应用配置上下文），创建方法如下：

   ```java
   	protected ConfigurableApplicationContext createApplicationContext() {
   		Class<?> contextClass = this.applicationContextClass;
   		if (contextClass == null) {
   			try {
   				switch (this.webApplicationType) {
   				case SERVLET:
   					contextClass = Class.forName(DEFAULT_SERVLET_WEB_CONTEXT_CLASS);
   					break;
   				case REACTIVE:
   					contextClass = Class.forName(DEFAULT_REACTIVE_WEB_CONTEXT_CLASS);
   					break;
   				default:
   					contextClass = Class.forName(DEFAULT_CONTEXT_CLASS);
   				}
   			}
   			catch (ClassNotFoundException ex) {
   				throw new IllegalStateException(
   						"Unable create a default ApplicationContext, "
   								+ "please specify an ApplicationContextClass",
   						ex);
   			}
   		}
   		return (ConfigurableApplicationContext) BeanUtils.instantiateClass(contextClass);
   	}
   ```

   方法会先获取显示设置的应用上下文（appcationContextClass），如果不存在，再加载默认的环境配置（通过是否是 web environment 判断），默认选择 AnnotationConfigApplicationContext 注解上下文（通过扫描所有注解类来加载 Bean），最后通过 BeanUtils 实例化上下文对象，并返回。

5. 回到 run 方法内，prepareContext 方法将 listeners、enviroment、applicationArguments、banner 等重要组件与上下文对象关联

6. 加下来的 refreshContext(context)方法（方法如下）是实现 spring-boot-starter-\*等自动化配置的关键，包括 spring.factories 的加载，bean 的实例化等核心工作

   ```java
   	@Override
   	public void refresh() throws BeansException, IllegalStateException {
   		synchronized (this.startupShutdownMonitor) {
   			// Prepare this context for refreshing.
   			prepareRefresh();

   			// Tell the subclass to refresh the internal bean factory.
   			ConfigurableListableBeanFactory beanFactory = obtainFreshBeanFactory();

   			// Prepare the bean factory for use in this context.
   			prepareBeanFactory(beanFactory);

   			try {
   				// Allows post-processing of the bean factory in context subclasses.
   				postProcessBeanFactory(beanFactory);

   				// Invoke factory processors registered as beans in the context.
   				invokeBeanFactoryPostProcessors(beanFactory);

   				// Register bean processors that intercept bean creation.
   				registerBeanPostProcessors(beanFactory);

   				// Initialize message source for this context.
   				initMessageSource();

   				// Initialize event multicaster for this context.
   				initApplicationEventMulticaster();

   				// Initialize other special beans in specific context subclasses.
   				onRefresh();

   				// Check for listener beans and register them.
   				registerListeners();

   				// Instantiate all remaining (non-lazy-init) singletons.
   				finishBeanFactoryInitialization(beanFactory);

   				// Last step: publish corresponding event.
   				finishRefresh();
   			}

   			catch (BeansException ex) {
   				if (logger.isWarnEnabled()) {
   					logger.warn("Exception encountered during context initialization - " +
   							"cancelling refresh attempt: " + ex);
   				}

   				// Destroy already created singletons to avoid dangling resources.
   				destroyBeans();

   				// Reset 'active' flag.
   				cancelRefresh(ex);

   				// Propagate exception to caller.
   				throw ex;
   			}

   			finally {
   				// Reset common introspection caches in Spring's core, since we
   				// might not ever need metadata for singleton beans anymore...
   				resetCommonCaches();
   			}
   		}
   	}
   ```

配置结束后，SpringBoot 做了一些基本的收尾工作，返回了应用环境上下文。总体而言，SpringBoot 的启动，主要创建了配置环境（environment）、事件监听（listener）、应用上下文（applicationContex），并基于以上条件，在容器中开始实例化我们需要的 Bean，最终完成 SpringBoot 的启动，这里面有一个核心就是自动化装配。

### 自动装配

在整个 SpringBoot 启动过程中，多出都调用了 SpringBoot 的自动装配模块

![图片](https://mmbiz.qpic.cn/mmbiz_png/6mychickmupWyfMiax0ryO6Hs4SYOv1IzQn8nK36PPIsEBpXXjQmX8ibniaohz5ahOYM5WnyicjgdYFa0Libxaztg6CQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

该配置模块主要使用到了 SpringFactoriesLoader，即 Spring 工厂加载器，该对象提供了 loadFactoryNames 方法，入参为 factoryClass 和 classLoader，即需要传入上图中的工厂类名称对应的类加载器，方法会根据指定的 classLoader，加载该类加载器搜索路径下的指定文件，即 spring.factories 文件，传入的工厂类为接口，而文件中对应的类则是接口的实现类，或最终作为实现类，所以文件中一般为下入这种一对多的类型集合，或者到这些实现类的类名后，loadFactoryNames 方法返回类名集合，方法调用方得到这些集合后，再通过反射获取这些类的类对象、构造方法，最终生成实例。

![图片](https://mmbiz.qpic.cn/mmbiz_png/6mychickmupWyfMiax0ryO6Hs4SYOv1IzQu9QicvqeO7RicwHibtCVtibnQHLmGxuKm0jw1ttR5mjBrqCIolBibRRo3icw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

自动配置流程如下：

<img src="https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210624211216303.png" alt="image-20210624211216303" style="zoom:50%;" />

`mybatis-spring-boot-starter`、`spring-boot-starter-web`等组件的 META-INF 文件下均含有`spring.factories`文件，自动配置模块中，`SpringFactoriesLoader`收集到文件中的类全名并返回一个类全名的数组，返回的类全名通过反射被实例化，就形成了具体的工厂实例，工厂实例来生成组件具体需要的 bean。

之前我们提到了`EnableAutoConfiguration`注解，其类图如下：

![图片](https://mmbiz.qpic.cn/mmbiz_png/6mychickmupWyfMiax0ryO6Hs4SYOv1IzQr8IZpibDYUkTRzFA4j2WWw7YFiciaZevFuxH1oSxMd0Jr7drDmILq3YMw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

可以发现其最终实现了`ImportSelector`(选择器)和`BeanClassLoaderAware`(bean 类加载器中间件)，重点关注一下`AutoConfigurationImportSelector`的`selectImports`方法。

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6mychickmupWyfMiax0ryO6Hs4SYOv1IzQticdcJNNcF5hWVAA4a5xib1D3qhoRf1lW9xQibDxiavYj2Ieicvzq7od95w/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

该方法在 springboot 启动流程——bean 实例化前被执行，返回要实例化的类信息列表。我们知道，如果获取到类信息，spring 自然可以通过类加载器将类加载到 jvm 中，现在我们已经通过 spring-boot 的 starter 依赖方式依赖了我们需要的组件，那么这些组建的类信息在 select 方法中也是可以被获取到的，不要急我们继续向下分析。

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6mychickmupWyfMiax0ryO6Hs4SYOv1IzQ7W4R5zDIcXoGv7Z12BlbAoqGQPGoR19rSFahPsiaqWfTLRqh7pZUQyA/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

该方法中的`getCandidateConfigurations`方法，通过方法注释了解到，其返回一个自动配置类的类名列表，方法调用了`loadFactoryNames`方法，查看该方法

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6mychickmupWyfMiax0ryO6Hs4SYOv1IzQGplWq8vdg5cDrXzLPyKPUZxgG5f1mN7eDYFaqrPfygKGib9QCWsmFTQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

在上面的代码可以看到自动配置器会根据传入的`factoryClass.getName()`到项目系统路径下所有的`spring.factories`文件中找到相应的 key，从而加载里面的类。我们就选取这个`mybatis-spring-boot-autoconfigure`下的`spring.factories`文件

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6mychickmupWyfMiax0ryO6Hs4SYOv1IzQBR85MD5HgVeib7Juia527ia5DedXvMDoZwibXtUvwIcIib3UsA1Z6eFKWgQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

进入`org.mybatis.spring.boot.autoconfigure.MybatisAutoConfiguration`中，主要看一下类头：

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6mychickmupWyfMiax0ryO6Hs4SYOv1IzQvDDF5STJSTOC9e5Nvou7NoyvgkdZHiam1ic8Hnz1cknuRM8lMLmVWicxw/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

发现 Spring 的`@Configuration`，俨然是一个通过注解标注的 springBean，继续向下看

- `@ConditionalOnClass({ SqlSessionFactory.class, SqlSessionFactoryBean.class})`：当存在`SqlSessionFactory.class`, `SqlSessionFactoryBean.class`这两个类时才解析`MybatisAutoConfiguration`配置类，否则不解析这一个配置类，make sence，我们需要 mybatis 为我们返回会话对象，就必须有会话工厂相关类
- `@CondtionalOnBean(DataSource.class)`：只有处理已经被声明为 bean 的 dataSource
- `@ConditionalOnMissingBean(MapperFactoryBean.class)`这个注解的意思是如果容器中不存在 name 指定的 bean 则创建 bean 注入，否则不执行（该类源码较长，篇幅限制不全粘贴）

以上配置可以保证`sqlSessionFactory、sqlSessionTemplate、dataSource`等 mybatis 所需的组件均可被自动配置，`@Configuration`注解已经提供了 Spring 的上下文环境，所以以上组件的配置方式与 Spring 启动时通过 mybatis.xml 文件进行配置起到一个效果。

通过分析我们可以发现，只要一个基于 SpringBoot 项目的类路径下存在`SqlSessionFactory.class`, `SqlSessionFactoryBean.class`，并且容器中已经注册了 dataSourceBean，就可以触发自动化配置，意思说我们只要在 maven 的项目中加入了 mybatis 所需要的若干依赖，就可以触发自动配置，但引入 mybatis 原生依赖的话，每集成一个功能都要去修改其自动化配置类，那就得不到开箱即用的效果了。

所以 Spring-boot 为我们提供了统一的 starter 可以直接配置好相关的类，触发自动配置所需的依赖(mybatis)如下：

![图片](https://mmbiz.qpic.cn/mmbiz_png/6mychickmupWyfMiax0ryO6Hs4SYOv1IzQKZibKhZCCVt3rXV9LD20lGHnKkLVfVjicblW5KJUQJnjHicxDicjB1WGYQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

这里是截取的`mybatis-spring-boot-starter`的源码中 pom.xml 文件中所有依赖：

![图片](https://mmbiz.qpic.cn/mmbiz_png/6mychickmupWyfMiax0ryO6Hs4SYOv1IzQTkmkxUoCMn3p5VBepEyVVA9YMKEiaJibrLsSDSeb1tibd20HiciauZx0S2w/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

因为 maven 依赖的传递性，我们只要依赖 starter 就可以依赖到所有需要自动配置的类，实现开箱即用的功能。也体现出 Springboot 简化了 Spring 框架带来的大量 XML 配置以及复杂的依赖管理，让开发人员可以更加关注业务逻辑的开发。

# SpringBoot 打包

## 打包过程

在 Spring Boot 应用中，我们可以约定不同的标识来定义不同的环境。例如 `dev` 表示开发环境、`test`表示测试环境，对应的配置文件为`application-dev.yaml`、`application-test.yaml`。我们通过声明`spring.profiles.active`来激活对应的环境配置，例如激活`dev`环境时`spring.profiles.active=dev`。完整的启动命令为：

```shell
java -Djava.security.egd=file:/dev/./urandom  -Dspring.profiles.active=dev -jar spring-boot-app.jar
```

根据上面的命令编写一个能够适应多环境的**Dockerfile**：

```shell
# 引入 openjdk 镜像
FROM adoptopenjdk/openjdk8
# 声明作者
LABEL AUTHOR=felord OG=felord.cn
# 挂载几个有用的文件夹 比如日志
VOLUME ["/tmp","/logs"]
# 声明一个环境参数用来动态启用配置文件 默认dev
ENV ACTIVE=dev
# 暴露端口
EXPOSE 8080
# 复制并修改应用打包后的jar文件名称
ADD /target/flyway-spring-boot-1.0.0.jar app.jar
# 容器启动时第一个运行的命令 用来启动应用
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-Dspring.profiles.active=${ACTIVE}","-jar","app.jar"]
```

这样打包的 Docker 镜像就可以通过`docker run`添加额外的`--env ACTIVE=test` 来动态的改变环境。单纯的编写**Dockerfile**不方便我们 DevOps。

![图片](https://mmbiz.qpic.cn/sz_mmbiz_png/zuF5sJGRDCvwCLZQv6fq6zEjyuBXHd9C5licH3DdoibYfYXGaQOZMiaibyQdeoyHGibNRfiab5Z2Z9Es2jX8DickH4hJw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

我们需要能够自动地构建、推送到仓库、拉取镜像、运行一系列流水线操作。好在市面上有很多工具来帮助我们实现这一过程。

## 构建工具

### spring-boot-maven-plugin

这个是 Spring Boot 官方的插件，在 2.x 的某个版本提供了 Docker 镜像构建能力。

```xml
<project>
 <build>
  <plugins>
   <plugin>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-maven-plugin</artifactId>
    <configuration>
     <image>
     <name>docker.repo.com/library/${project.artifactId}:${project.version}</name>
      <publish>true</publish>
     </image>
     <docker>
      <publishRegistry>
       <username>user</username>
       <password>secret</password>
       <url>https://docker.repo.com/v1/</url>
       <email>user@example.com</email>
      </publishRegistry>
     </docker>
    </configuration>
   </plugin>
  </plugins>
 </build>
</project>
```

配置好 Docker 私仓后就可以通过`mvn clean spring-boot:build-image` 进行构建镜像了，这种方式好处就是无额外依赖，缺点就是需要从 github 下载构建元件，网络如果不好就容易失败。

### Spotify Maven Plugin

Spotify Maven 插件是一个目前比较普遍的选择。它要求应用程序开发人员编写**Dockerfile**，并把`Dockerfile`放在项目`src/main/docker`目录下。然后你就可以通过引入：

```xml
 <plugin>
     <groupId>com.spotify</groupId>
     <artifactId>dockerfile-maven-plugin</artifactId>
     <version>1.4.8</version>
     <configuration>
         <repository>repo.com/${project.artifactId}</repository>
     </configuration>
</plugin>
```

这个插件提供了`mvn dockerfile:build`、`mvn dockerfile:tag`、`mvn dockerfile:push`三个命令分别用来构建、打标签、发布到远端私有仓库，非常简单。

这个是一个非常容易上手的插件，唯一的要求就是需要会编写 Dockerfile，对定制化要求高的可以使用这个。

### Jib Maven Plugin

它是谷歌开源的 OCI 镜像打包工具，可以用来打包 Docker 镜像，大部分情况下已经满足需要。但是如果你要定制化的话还是不容易的，需要阅读官方给的文档。最开始的**Dockerfile**如果使用**JIb**的话需要这样配置：

```xml
<plugin>
    <groupId>com.google.cloud.tools</groupId>
    <artifactId>jib-maven-plugin</artifactId>
    <version>3.0.0</version>
    <configuration>
        <from>
            <image>adoptopenjdk/openjdk8</image>
        </from>
        <to>
            <image>docker.repo.com/library/${project.artifactId}</image>
            <auth>
                <username>felord</username>
                <password>xxxxxx</password>
            </auth>
            <tags>
                <tag>${project.version}</tag>
            </tags>
        </to>
        <extraDirectories>
            <paths>
                <path>
                    <from>target/${project.artifactId}-${project.version}.jar</from>
                    <includes>*.jar</includes>
                    <into>/app.jar</into>
                </path>
            </paths>
        </extraDirectories>
        <containerizingMode>packaged</containerizingMode>
        <container>
            <volumes>/tmp,/logs</volumes>
            <ports>
                <port>8080</port>
            </ports>
            <environment>
                <active>dev</active>
            </environment>
            <entrypoint>
                java,-Djava.security.egd=file:/dev/./urandom,-Dspring.profiles.active=${active},-jar,/app.jar
            </entrypoint>
            <creationTime>USE_CURRENT_TIMESTAMP</creationTime>
        </container>
    </configuration>
</plugin>
```

优点是不需要本地 Docker 环境，而且支持分层构建、镜像瘦身，上手容易；缺点是定制化比较困难。

# SpringBoot 项目 docker 打包体积优化

## 修改之前

最开始使用的 dockerfile：

```dockerfile
FROM java:8

# 环境变量
ENV WORK_PATH /home/project/cmp
ENV APP_NAME @project.build.finalName@.@project.packaging@
ENV APP_VERSION @project.version@

EXPOSE 8080

#VOLUME
VOLUME ["/home/project", "/tmp/data"]

#COPY
COPY $APP_NAME $WORK_PATH/

# WORKDIR
WORKDIR $WORK_PATH

RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
RUN echo 'Asia/Shanghai' >/etc/timezone

COPY SIMSUN.TTC  /usr/share/fonts/SIMSUN.TTC
RUN cd  /usr/share/fonts
RUN fc-cache -fsv

# ENTRYPOINT
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom"]

CMD ["-jar", "-Xmx512m", "@project.build.finalName@.@project.packaging@"]
```

由于这里直接使用 java8 的镜像，本身就有 600 多 M，加上业务模块本身的大小，大约有了 800 多 M，这样每次打包构建，非常的耗时，也很占用磁盘空间。

![image-20210624210110566](https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210624210110566.png)

## 使用 Alpine 镜像

`Alpine Linux`操作系统是一个面向安全的轻型 `Linux` 发行版，`Alpine Docker` 镜像也继承了`Alpine Linux`发行版的这些优势，相比于其他 Docker 镜像，它的容量非常小，并且拥有自己的包管理机制，可以使用`apk` 包管理器替换 `apt` 工具，例如：

```shell
$ apk add --no-cache <package>
```

这里我们使用 Alpine 提供的 docker 镜像：

![image-20210624210052799](https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210624210052799.png)

因此这里我们使用`Alpine`镜像，并且将 RUN 的指令合并在一起，减少构建的层数，修改之后的 dockerfile，：

```dockerfile
FROM openjdk:8-jdk-alpine

# 环境变量
ENV WORK_PATH /home/project/cmp
# 这里的都是maven内置的变量
ENV APP_NAME @project.build.finalName@.@project.packaging@

COPY $APP_NAME $WORK_PATH/

# WORKDIR
WORKDIR $WORK_PATH
# 根据实际需求添加字体
COPY simsun.ttc  /usr/share/fonts/simsun.ttc
# 为了解决docker容器内的时间和宿主机时间不一致的问题，并且安装了fontconfig，方便安装字体
RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo 'Asia/Shanghai' >/etc/timezone && apk add --update ttf-dejavu fontconfig && rm -rf /var/cache/apk/*

# ENTRYPOINT
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom"]

CMD ["-jar", "-Xmx512m", "@project.build.finalName@.@project.packaging@"]
```

## 分层构建镜像

使用了`Alpine`镜像之后，项目的体积有了比较明显的改善，但是每次打包的时候还是会全量构建项目中的所有内容，构建的时间还是比较长，这里我们使用分层的机制来进行打包，这里要注意的是，使用的`SpringBoot`的版本必须要大于 2.3.X。

```dockerfile
FROM openjdk:8-jdk-alpine as builder
ENV APP_NAME @project.build.finalName@.@project.packaging@
WORKDIR application
# 注意这里对应的是编译后的dockerfile的目录，如果对应不上，可能会提示找不到文件
COPY $APP_NAME application.jar
# 指定构建Jar的模式，并从Jar包中提取构建镜像所需的内容
RUN java -Djarmode=layertools -jar application.jar extract

FROM openjdk:8-jdk-alpine
WORKDIR application
# 拷贝字体，这里安装宋体字体，alpine镜像会自动检测/usr/share/fonts是否含有字体
COPY simsun.ttc  /usr/share/fonts/simsun.ttc
COPY --from=builder application/dependencies/ ./
COPY --from=builder application/snapshot-dependencies/ ./
COPY --from=builder application/spring-boot-loader/ ./
COPY --from=builder application/application/ ./
ENV TZ="Asia/Shanghai"
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
# 设置虚拟机参数
ENV JVM_OPTS="-XX:MaxRAMPercentage=80.0"
ENV JAVA_OPTS=""
ENTRYPOINT ["sh","-c","java $JVM_OPTS $JAVA_OPTS org.springframework.boot.loader.JarLauncher"]
```

配置 pom.xml 文件：

```xml
<plugin>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-maven-plugin</artifactId>
    <!--引用本地Jar包-->
    <configuration>
        <includeSystemScope>true</includeSystemScope>
        <layers>
            <enabled>
                true
            </enabled>
        </layers>
    </configuration>
</plugin>
```

## Maven 中内置变量

- `${basedir}` 项目根目录
- `${project.build.directory}` 构建目录，缺省为 target
- `${project.build.outputDirectory}` 构建过程输出目录，缺省为 target/classes
- `${project.build.finalName}` 产出物名称，缺省为{project.artifactId}-${project.version}
- `${project.packaging}` 打包类型，缺省为 jar
- `${project.xxx}` 当前 pom 文件的任意节点的内容

## 可能存在的问题

1. 如果本身项目`SpringBoot`版本较低，不建议升级，推荐通过使用`Alpine`镜像以及优化 dockerfile 写法减少镜像体积，特别的，如果是使用的`Spring Cloud`，升级会出现组件版本不兼容的情况，可能需要升级诸多依赖的版本，并且需要投入精力进行测试验证。

2. 如果项目不需要字体，可以跳过：

   ```shell
   RUN apk add --update ttf-dejavu fontconfig && rm -rf /var/cache/apk/*
   ```

3. 如果项目中只需要宋体，可以只复制字体文件到镜像内，而不需要安装 fontconfig，`alpine`镜像会自动检测`/usr/share/fonts`是否含有字体：

   ```shell
   COPY simsun.ttc  /usr/share/fonts/simsun.ttc
   ```

4. 如果项目中既需要宋体又需要其他字体（例如图片验证码），这是时候，拷贝宋体字体文件和安装 fontconfig 都需要：

   ```shell
   COPY simsun.ttc  /usr/share/fonts/simsun.ttc
   RUN apk add --update ttf-dejavu fontconfig && rm -rf /var/cache/apk/*
   ```

5. 如果镜像打包的体积还是过大，可以使用`docker history image_name --no-trunc=true`命令来查看构建的详情。

附完整的 pom 文件：

```xml
  <build>
        <resources>
            <resource>
                <directory>src/main/resources</directory>
                <filtering>true</filtering>
                <includes>
                    <include>application-${profiles.active}.yml</include>
                    <include>bootstrap.yml</include>
                    <include>application.yml</include>
                </includes>
            </resource>
            <!--这里实我们的dockerfile文件所在的目录-->
            <resource>
                <directory>src/main/docker</directory>
                <filtering>true</filtering>
                <includes>
                    <include>**/Dockerfile</include>
                </includes>
                <targetPath>../docker</targetPath>
            </resource>
            <resource>
                <directory>src/main/resources</directory>
                <filtering>true</filtering>
                <includes>
                    <include>static/**</include>
                    <include>**/*.jar</include>
                    <include>bootstrap.yml</include>
                    <include>*.yml</include>
                    <include>*.xml</include>
                </includes>
            </resource>
            <resource>
                <directory>src/main/java</directory>
                <includes>
                    <include>**/*.xml</include>
                    <include>**/*.json</include>
                    <include>**/*.ftl</include>
                </includes>
            </resource>
        </resources>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
                <!--引用本地Jar包-->
                <configuration>
                    <includeSystemScope>true</includeSystemScope>
                    <layers>
                        <enabled>
                            true
                        </enabled>
                    </layers>
                </configuration>
            </plugin>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <configuration>
                    <source>1.8</source>
                    <target>1.8</target>
                    <encoding>UTF-8</encoding>
                </configuration>
            </plugin>
            <!-- 打包跳过测试 -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-surefire-plugin</artifactId>
                <configuration>
                    <skipTests>true</skipTests>
                </configuration>
            </plugin>
            <!-- 避免font文件的二进制文件格式压缩破坏 -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-resources-plugin</artifactId>
                <configuration>
                    <nonFilteredFileExtensions>
                        <nonFilteredFileExtension>woff</nonFilteredFileExtension>
                        <nonFilteredFileExtension>woff2</nonFilteredFileExtension>
                        <nonFilteredFileExtension>eot</nonFilteredFileExtension>
                        <nonFilteredFileExtension>ttf</nonFilteredFileExtension>
                        <nonFilteredFileExtension>svg</nonFilteredFileExtension>
                    </nonFilteredFileExtensions>
                    <delimiters>
                        <delimiter>@</delimiter>
                    </delimiters>
                    <useDefaultDelimiters>false</useDefaultDelimiters>
                </configuration>
            </plugin>
            <plugin>
                <groupId>com.spotify</groupId>
                <artifactId>docker-maven-plugin</artifactId>
                <version>1.1.0</version>
                <executions>
                    <execution>
                        <id>build-image</id>
                        <phase>package</phase>
                        <goals>
                            <goal>build</goal>
                        </goals>
                    </execution>
                    <execution>
                        <id>push-image</id>
                        <phase>package</phase>
                        <goals>
                            <goal>push</goal>
                        </goals>
                        <configuration>
                            <imageName>
                                ${docker.repostory}/${docker.registry.name}/${project.artifactId}:${profiles.active}-${project.version}
                            </imageName>
                        </configuration>
                    </execution>
                </executions>
                <configuration>
                    <serverId>harbor</serverId>
                    <dockerDirectory>${project.build.directory}/docker</dockerDirectory>
                    <imageName>
                        ${docker.repostory}/${docker.registry.name}/${project.artifactId}
                    </imageName>
                    <imageTags>
                        <!--docker的tag为项目版本号、latest-->
                        <imageTag>${profiles.active}-${project.version}</imageTag>
                    </imageTags>
                    <resources>
                        <rescource><!-- 将打包文件放入dockerDirectory指定的位置 -->
                            <targetPath>/</targetPath>
                            <directory>${project.build.directory}</directory>
                            <include>${project.artifactId}-${project.version}.jar</include>
                        </rescource>
                    </resources>
                </configuration>
            </plugin>
        </plugins>
    </build>
```
