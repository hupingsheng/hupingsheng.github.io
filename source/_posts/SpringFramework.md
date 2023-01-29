---
title: SpringFramework
date: 2020-07-16
categories:
  - Spring
tags:
  - Spring
  - SpringBoot
  - Java
author: 胡先森
top: 2
---

Spring 毫无疑问是当下 Web 开发的事实标准，修炼好 Web 开发中这一门最为重要的内功，对于框架原理的理解、视野的开拓以及学习周边技术栈是必不可少的。

<!-- more -->

# Spring 基础

## Spring 特性总览

### Spring 中值得学习的地方

1. Java 语言特性，例如反射、动态代理、枚举、泛型、注解、ARM、Lambda 语法
2. 设计思想和模式的实现，如 OOP，DDD，TDD，GoF23 等
3. Java API 的封装与简化，如 JDBC，事务，Transaction，Servlet，JPA，JMX ，Bean Validation
4. JSR 规范的适配与实现
5. 第三方框架的整合，如 MyBatis 整合 Hibernetes 和 Redis

### Spring 核心特性

1. IOC 容器（IOC Container）
2. Spring 事件（Events）
3. 资源管理（Resources）
4. 国际化（i18n）
5. 校验（Validation）
6. 数据绑定（Data Binding）
7. 类型转换（Type Conversion）
8. Spring 表达式（Spring Express Language）
9. 面向切面编程（AOP）

### Spring 数据存储

1. JDBC
2. 事务抽象（Transactions）
3. DAO 支持（DAO Support）
4. O/R 映射（O/R Mapping）
5. XML 编列（XML Marshalling）

### Spring Web 技术

1. Web Servlet 技术栈
   1. Spring MVC
   2. WebSocket
   3. SockJS
2. Web Reactive 技术栈
   1. Spring WebFlux
   2. WebClient
   3. WebSocket

### Spring 技术整合

1. 远程调用（Remoting）
2. Java 消息服务（JMS）
3. Java 连接架构（JCA）
4. Java 管理扩展（JMX）
5. Java 邮件客户端（Email）
6. 本地任务（Taks）
7. 本地调度（Scheduling）
8. 缓存抽象（Caching）

### Spring 测试

1. 模拟对象（Mock Objects）
2. TestContext 框架（TestContext Framework）
3. Spring MVC 测试（Spring MVC Test）
4. Web 测试客户端（Web TestClient）

## Spring 版本特性

| Spring Framework 版本 | Java 标准版 | Java 企业版        |
| --------------------- | ----------- | ------------------ |
| 1.x                   | 1.3+        | J2EE 1.3+          |
| 2.x                   | 1.4.2+      | J2EE 1.3+          |
| 3.x                   | 5+          | J2EE1.4 和 JavaEE5 |
| 4.x                   | 6+          | Java EE6 和 7      |
| 5.x                   | 8+          | Java EE7           |

## Spring 模块化设计

[仓库链接](https://github.com/spring-projects/spring-framework)

![image-20210624205130273](https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210624205130273.png)

## Spring 编程模型

1. 面向对象编程

   1. 锲约接口：Aware、BeanPostProcessor...
   2. 设计模式：观察者模式、组合模式、模板模式...
   3. 对象继承：Abstract 类

2. 面向切面编程

   1. 动态代理：JDKDynamicAopProxy
   2. 字节码提升：ASM、CGLib、AspectJ

3. 面向元编程

   1. 注解：模式注解（@Component、@Service、@Respository...）
   2. 配置：Environment 抽象、PropertySources、BeanDefinition...
   3. 泛型：Generic TypeResolver、Resolvable Type...

4. 函数驱动

   1. 函数接口：ApplicationEventPublisher
   2. Reactive：Spring WebFlux

5. 模块驱动

   1. Maven Artifacts
   2. OSGI Bundies
   3. Java 9 Automatic Modules
   4. Spring @Enable\*

   ​

## Spring 的核心价值

1. 生态系统
   1. Spring Boot
   2. Spring Cloud
   3. Spring Security
   4. Spring Data
   5. 其他
2. API 抽象设计
   1. AOP 抽象
   2. 事务抽象
   3. Environment 抽象
   4. 生命周期
3. 编程模型
   1. 面向对象编程：契约接口
   2. 面向切面编程：动态代理、字节码提升
   3. 面向元编程：配置元信息、注解、配置
   4. 面向模块编程：Maven Artifacts、Java9 Automatic Modules
   5. Spring @Enable\*注解
   6. 面向函数式编程：Lambda、Reactive
4. 设计思想
   1. Object-Oriented Programming（OOP）
   2. Ioc/DI
   3. Domain-Driven Development（DDD）
   4. Test-Driven Development（TDD）
   5. Event-Driven Programing（EDP）
   6. Functional Programing（FP）
5. 设计模式
   1. 专属模式
      1. 前缀模式：Enable 模式
         1. Configurable 模式
      2. 后缀模式
         1. 处理器模式（Process、Resolver、Handler）
         2. 意识模式（Aware）
         3. 配置器模式（Configuror）
         4. 选择器模式（ImportSelector）
   2. 传统 GoF23
6. 用户基础
   1. Spring 用户 Spring Framework、SpringBoot、Spring Cloud
   2. 传统用户 Java SE、Java EE

## 面试题

### 什么是 Spring Framework？

Spring Framework 提供一个完整性的编程或配置的一个现代化的基于 Java 的企业的应用，Spring 的核心特点是在应用级别上的基础设施建设。

Spring 使得你的应用开发变的更容易，它可以提供任何你想要的东西，并是拥抱企业环境的 Java 语言，并且支持可以运行在 JVM 上面的其他语言，比如 Groovy 或者 Kotlin，同时也提供一些弹性，根据软件的需要提供不同的软件架构。

### Spring Framwork 有哪些核心模块？

1. Spring-core：Spring 基础 API 模块，如资源管理、泛型处理
2. Spring-beans：Spring Bean 相关，如依赖查找，依赖注入
3. Spring-aop：Spring AOP 处理，如动态代理，AOP 字节码提升
4. Spring-context：事件驱动、注解驱动、模块驱动
5. Spring-expresson：Spring 表达式语言模块

### Spring Framework 的优势和不足是什么？

待定...

# IoC 简介

## IoC 的发展简介

1. 1983 年，好莱坞原则
2. 1988 年，控制反转
3. 1996 年，Inversion of control -> Hollywood principle
4. 2004 年，Martin Fowler 提出了自己对 IoC 以及 DI 的理解
5. 2005 年，Martin Fowler 对 IoC 做出了进一步的说明

## IoC 主要实现策略

1. 使用 service locator pattern（服务定位模式）
2. 通过依赖注入：
   1. 构造器注入
   2. 参数注入
   3. Setter 注入
   4. 接口注入
3. 上下文的依赖查询（beancontext）
4. 模板方法设计模式（例如 JDBC）
5. 策略模式

IoC 主要的实现策略：依赖查找、依赖注入。

## IoC 容器的职责

1. 依赖处理
   1. 依赖查找
   2. 依赖注入
2. 生命周期管理
   1. 容器
   2. 托管的资源（Java Beans 或其他资源）
3. 配置
   1. 容器
   2. 外部化配置
   3. 托管的资源（Java Beans 或其他资源）

## IoC 的实现

1. Java SE
   - Java Beans
   - Java ServiceLoader SPI
   - JNDI（Java Naming and Directory Interface）
2. Java EE
   - EJB（Enterprise Java Beans）
   - Servlet
3. 开源
   - Apache Avalon
   - PicoContainer
   - Google Guice
   - Spring Framework

## 传统 IoC 容器的实现

Java Beans 作为 IoC 容器的特性：

- 依赖查找
- 生命周期管理
- 配置元信息
- 事件
- 自定义
- 资源管理
- 持久化

什么是 Java Beans 呢？

```java
/**
 * 描述人的POJO类
 */
public class Person {

    String name;

    Integer age;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public Integer getAge() {
        return age;
    }

    public void setAge(Integer age) {
        this.age = age;
    }
}
```

我们可以打印这个 Bean 的元信息：

```java
public class BeanInfoDemo {
    public static void main(String[] args) throws Exception {
        BeanInfo beanInfo = Introspector.getBeanInfo(Person.class, Object.class);
        Stream.of(beanInfo.getPropertyDescriptors()).forEach(System.out::println);
    }
}
```

打印结果：

```txt
java.beans.PropertyDescriptor[name=age; propertyType=class java.lang.Integer; readMethod=public java.lang.Integer beans.Person.getAge(); writeMethod=public void beans.Person.setAge(java.lang.Integer)]
java.beans.PropertyDescriptor[name=name; propertyType=class java.lang.String; readMethod=public java.lang.String beans.Person.getName(); writeMethod=public void beans.Person.setName(java.lang.String)]
```

## 如何界定 IoC 容器是轻量级的？

以下观点出自于《J2EE Development without EJB》

1. 管理应用代码
2. 能够快速启动
3. 容器不需要一些特殊的配置来进行操作（主要是针对于 EJB）
4. 容器的内存占用小以及最小化 API 的一个依赖
5. 容器需要一些可以管控的一个渠道，这个渠道能够帮助我们去部署和管理一些细粒度的对象，甚至是一些粗粒度的组件

## 依赖查找和依赖注入

| 类型     | 依赖处理 | 实现便利性 | 代码入侵性   | API 依赖性         | 可读性 |
| -------- | -------- | ---------- | ------------ | ------------------ | ------ |
| 依赖查找 | 主动获取 | 相对繁琐   | 侵入业务逻辑 | 依赖容器 API       | 良好   |
| 依赖注入 | 被动提供 | 相对便利   | 低入侵性     | 不主动依赖容器 API | 一般   |

## 构造器注入和 Setter 注入

Spring 官方推荐使用构造器注入，这样可以确保在注入时，对象不为空，但是参数过多时会影响代码的整洁性，可能需要考虑重构。

Setter 注入应该主要仅用于我们的可选性的注入，因为 Setter 的字段本身是可以为空的。

而《J2EE Development without EJB》认为应该使用 Setter 注入，原因在于：

1. JavaBean 属性能够获取更好的 IDE 支持
2. JavaBean 属性通常是一个自文档的说明
3. 在类型转换上有优势
4. 大量的 JavaBeans 可能不经过任何修改就可以在 JavaBean 容器当中使用

当然，Setter 注入也有缺点，就是无法确定属性初始化的顺序。

## 面试题

### 什么是 IoC？

简单地说，IoC 是反转控制，类似于好莱坞原则，主要有依赖查找和依赖注入两种实现。按照 IoC 的定义，很多方面其实都是 IoC，比如 JavaBeans 是 IoC 的一个容器实现，Servlet 的容器也是 IoC 的实现，因为 Servlet 可以去依赖或者反向地通过 JNDI 的方式进行得到一些外部的一些资源，包括 DataSource 或者相关的 EJB 的组件，于此同时 SpringFramework 或者 Peak Container 的依赖注入的框架，也能帮助我们去实现 IoC，除此之外，消息也可以看作是 IoC 的一种实现。

### 依赖查找和依赖注入的区别？

依赖查找是主动或手动的依赖查找方式，通常需要依赖容器或标准 API 实现。而依赖注入则是手动或自动依赖绑定的方式，无需依赖特定的容器和 API。

### Spring 作为 IoC 容器有什么优势？

典型的 IoC 管理，依赖查找和依赖注入，AOP 抽象，事务抽象，事件机制，SPI 扩展，强大的第三方整合，易测试性，更好的面向对象。

# IoC 实践

## Spring IoC 依赖查找

1. 根据 Bean 名称查找
   - 实时查找
   - 延迟查找
2. 根据 Bean 类型查找
   - 单个 Bean 对象
   - 集合 Bean 对象
3. 根据 Bean 名称+类型查找
4. 根据 Java 注解查找

新建一个用户类：

```java
/**
 * 用户类
 */
public class User {
    private String id;

    private String name;

    public String getId() {
        return id;
    }

    public void setId(String id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "User{" +
                "id='" + id + '\'' +
                ", name='" + name + '\'' +
                '}';
    }
}
```

新建一个超级用户类：

```java
/**
 * 超级用户
 */
@Super
public class SuperUser extends User{

    private String address;

    public String getAddress() {
        return address;
    }

    @Override
    public String toString() {
        return "SuperUser{" +
                "address='" + address + '\'' +
                "} " + super.toString();
    }

    public void setAddress(String address) {
        this.address = address;
    }
}
```

新建一个注解：

```java
/**
 * 超级
 */
@Target(ElementType.TYPE)
@Retention(RetentionPolicy.RUNTIME)
public @interface Super {
}

```

向容器中注入一些 Bean：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="user" class="org.jyc.thinking.in.spring.ioc.overview.dependency.domain.User">
        <property name="id" value="1"/>
        <property name="name" value="胡先森" />
    </bean>

    <bean id="SuperUser" class="org.jyc.thinking.in.spring.ioc.overview.dependency.domain.SuperUser" parent="user" primary="true">
        <property name="address" value="深圳" />
    </bean>

    <bean id="objectFactory" class="org.springframework.beans.factory.config.ObjectFactoryCreatingFactoryBean">
        <property name="targetBeanName" value="user"></property>
    </bean>
</beans>
```

依赖查找的示例：

```java
public class DependencyLookupDemo {
    public static void main(String[] args) {
        // 配置XML文件
        // 启动Spring应用上下文
        BeanFactory beanFactory = new ClassPathXmlApplicationContext("META-INF/dependency-lookup-context.xml");
        // 实时查找
        lookupInRealTime(beanFactory);
        // 延迟查找
        lookupInLazy(beanFactory);
        // 按照类型查找
        lookupByType(beanFactory);
        // 按照类型查找集合对象
        lookupCollectionType(beanFactory);
        // 通过注解查找
        lookupByAnnotationType(beanFactory);
    }

    /**
     * 通过注解查找
     * @param beanFactory
     */
    private static void lookupByAnnotationType(BeanFactory beanFactory) {
        if (beanFactory instanceof ListableBeanFactory) {
            ListableBeanFactory listableBeanFactory = (ListableBeanFactory) beanFactory;
            Map<String, User> users = (Map)listableBeanFactory.getBeansWithAnnotation(Super.class);
            System.out.println("查找到的所有标注@Super的User集合对象：" + users);
        }
    }

    /**
     * 按照类型查找集合对象
     * @param beanFactory
     */
    private static void lookupCollectionType(BeanFactory beanFactory) {
        if (beanFactory instanceof ListableBeanFactory) {
            ListableBeanFactory listableBeanFactory = (ListableBeanFactory) beanFactory;
            Map<String, User> users = listableBeanFactory.getBeansOfType(User.class);
            System.out.println("查找到的所有的User集合对象：" + users);
        }
    }

    /**
     * 按照类型查找
     * @param beanFactory
     */
    private static void lookupByType(BeanFactory beanFactory) {
        User user = beanFactory.getBean(User.class);
        System.out.println("按照类型查找 " + user);

    }

    /**
     * 延迟查找
     *
     * @param beanFactory
     */
    private static void lookupInLazy(BeanFactory beanFactory) {
        ObjectFactory<User> objectFactory = (ObjectFactory<User>) beanFactory.getBean("objectFactory");
        User user = objectFactory.getObject();
        System.out.println("延迟查找 " + user);
    }

    /**
     * 实时查找
     *
     * @param beanFactory
     */
    private static void lookupInRealTime(BeanFactory beanFactory) {
        User user = (User) beanFactory.getBean("user");
        System.out.println("实时查找" + user);
    }
}
```

## Spring IoC 依赖注入

1. 根据 Bean 名称注入
2. 根据 Bean 类型注入
   - 单个 Bean 对象
   - 集合 Bean 对象
3. 注入容器内建的 Bean 对象
4. 注入非 Bean 对象
5. 注入类型
   - 实时注入
   - 延迟注入

```java
/**
 * 用户信息仓库
 */
public class UserRespository {

    private Collection<User> users; // 自定义Bean

    private BeanFactory beanFactory; //内建的非Bean对象（对象）

    private ObjectFactory<ApplicationContext> objectFactory;

    public Collection<User> getUsers() {
        return users;
    }

    public void setUsers(Collection<User> users) {
        this.users = users;
    }

    public void setBeanFactory(BeanFactory beanFactory) {
        this.beanFactory = beanFactory;
    }

    public ObjectFactory<ApplicationContext> getObjectFactory() {
        return objectFactory;
    }

    public void setObjectFactory(ObjectFactory<ApplicationContext> objectFactory) {
        this.objectFactory = objectFactory;
    }

    public BeanFactory getBeanFactory() {
        return beanFactory;
    }
}
```

定义一个类似的资源：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:util="http://www.springframework.org/schema/util"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <!-- 通过导入复用   -->
    <import resource="dependency-lookup-context.xml" />

    <!--   Auto-wiring     -->
    <bean id="userRespository" class="org.jyc.thinking.in.spring.ioc.overview.dependency.repository.UserRespository" autowire="byType">
        <!--   手动配置     -->
<!--        <property name="users">-->
<!--            <util:list>-->
<!--                <ref bean="user"></ref>-->
<!--                <ref bean="SuperUser"></ref>-->
<!--            </util:list>-->
<!--        </property>-->
    </bean>
</beans>
```

测试：

```java
public class DependencyInjectionDemo {
    public static void main(String[] args) {
        // 配置XML文件
        // 启动Spring应用上下文
        BeanFactory beanFactory = new ClassPathXmlApplicationContext("META-INF/dependency-injection-context.xml");

        UserRespository userRespository = beanFactory.getBean("userRespository", UserRespository.class);
//        System.out.println(userRespository.getUsers());
        System.out.println(userRespository.getBeanFactory());
//        System.out.println(userRespository.getBeanFactory() == beanFactory);
        ObjectFactory<ApplicationContext> userFactory = userRespository.getObjectFactory();
        System.out.println(userFactory.getObject() == beanFactory);

    }
}
```

对比结果可以发现依赖查找和依赖注入的来源并不一样。

## Spring 依赖注入和依赖查找的来源

1. 自定义 Bean
2. 容器内建 Bean 对象
3. 容器内建依赖

```java
public class DependencyInjectionDemo {
    public static void main(String[] args) {
        // 配置XML文件
        // 启动Spring应用上下文
        BeanFactory beanFactory = new ClassPathXmlApplicationContext("META-INF/dependency-injection-context.xml");
        // 自定义的Bean
        UserRespository userRespository = beanFactory.getBean("userRespository", UserRespository.class);
        // 依赖注入（内建依赖）
        System.out.println(userRespository.getBeanFactory());
        // 容器内建Bean对象
        Environment environment = beanFactory.getBean(Environment.class);

        System.out.println("获取Enviroment类型的Bean" + environment);

    }
}
```

## Spring IoC 配置元信息

1. Bean 定义配置
   - 基于 XML 文件
   - 基于 Properties 文件
   - 基于 Java 注解
   - 基于 Java API（专题讨论）
2. IoC 容器配置
   - 基于 XML 文件
   - 基于 Java 注解
   - 基于 Java API（专题讨论）
3. 外部化属性配置
   - 基于 Java 注解

## BeanFactory 和 ApplicationContext

BeanFactory 和 ApplicationContext 谁才是 Spring IoC 容器？

BeanFactory 是一个具有基本功能的框架，而 ApplicationContext 添加了更多企业级的特性，总而言之，ApplicationContext 是 BeanFactory 的超集，并且在实现上，ApplicationContext 虽然继承了 BeanFactory 接口，但内部的 BeanFactory 是采用组合的方式进行的实现，默认的实现类为 DefaultListableBeanFactory。

ApplicationContext 除了 IoC 容器角色，还有提供：

- 面向切面（AOP）
- 配置元信息（Configuration Metadata）
- 资源管理（Resources）
- 事件（Events）
- 国际化（i18n）
- 注解（Annotations）
- Environment 抽象（Environment Abstraction）

BeanFactory 的 IoC 容器的使用：

```java
/**
 * BeanFactory作为IoC容器示例
 */
public class BeanFactoryAsIoCContainerDemo {
    public static void main(String[] args) {
        // 创建BeanFactory容器
        DefaultListableBeanFactory beanFactory = new DefaultListableBeanFactory();
        // 加载配置
        XmlBeanDefinitionReader reader = new XmlBeanDefinitionReader(beanFactory);
        // XML配置文件ClassPath路径
        String location = "classpath:/META-INF/dependency-lookup-context.xml";
        // 加载配置
        int beanDefinitions = reader.loadBeanDefinitions(location);
        System.out.println("Bean定义加载的数量: " + beanDefinitions);
        // 依赖查找集合对象....
        lookupCollectionType(beanFactory);
    }

    /**
     * 按照类型查找集合对象
     * @param beanFactory
     */
    private static void lookupCollectionType(BeanFactory beanFactory) {
        if (beanFactory instanceof ListableBeanFactory) {
            ListableBeanFactory listableBeanFactory = (ListableBeanFactory) beanFactory;
            Map<String, User> users = listableBeanFactory.getBeansOfType(User.class);
            System.out.println("查找到的所有的User集合对象：" + users);
        }
    }
}
```

Application 的 IoC 容器使用：

```java
/**
* ApplicationA作为IoC容器示例
*/
public class AnnotationApplicationAsIoCContainerDemo {
   public static void main(String[] args) {
       // 创建BeanFactory容器
       AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
       applicationContext.register(AnnotationApplicationAsIoCContainerDemo.class);
       applicationContext.refresh();
       // 依赖查找集合对象....
       lookupCollectionType(applicationContext);
   }

   @Bean
   public User user() {
       User user = new User();
       user.setId("1");
       user.setName("胡先森");
       return user;
   }

   /**
    * 按照类型查找集合对象
    * @param beanFactory
    */
   private static void lookupCollectionType(BeanFactory beanFactory) {
       if (beanFactory instanceof ListableBeanFactory) {
           ListableBeanFactory listableBeanFactory = (ListableBeanFactory) beanFactory;
           Map<String, User> users = listableBeanFactory.getBeansOfType(User.class);
           System.out.println("查找到的所有的User集合对象：" + users);
       }
   }
}
```

可以看到，使用 BeanFactory 和 ApplicationContext 都可以完成依赖查找的功能。

## Spring IoC 容器生命周期

```java
	public void refresh() throws BeansException, IllegalStateException {
		synchronized (this.startupShutdownMonitor) {
			StartupStep contextRefresh = this.applicationStartup.start("spring.context.refresh");

			// Prepare this context for refreshing.
			prepareRefresh();

			// Tell the subclass to refresh the internal bean factory.
			ConfigurableListableBeanFactory beanFactory = obtainFreshBeanFactory();

			// Prepare the bean factory for use in this context.
			prepareBeanFactory(beanFactory);

			try {
				// Allows post-processing of the bean factory in context subclasses.
				postProcessBeanFactory(beanFactory);

				StartupStep beanPostProcess = this.applicationStartup.start("spring.context.beans.post-process");
				// Invoke factory processors registered as beans in the context.
				invokeBeanFactoryPostProcessors(beanFactory);

				// Register bean processors that intercept bean creation.
				registerBeanPostProcessors(beanFactory);
				beanPostProcess.end();

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
				contextRefresh.end();
			}
		}
	}
```

## 面试题

### 什么是 Spring IoC 容器

Spring Framework 是 IoC（控制反转）的一种具体的实现，主要包括了 DI（dependency injection），和 DL（dependency lookup）。

### BeanFactory 和 FactoryBean

BeanFactory 是 IoC 底层容器，FactoryBean 是创建 Bean 的一种方式，帮助实现复杂的初始化逻辑。

### Spring IoC 容器启动时做了哪些准备？

IoC 配置元信息读取和解析、IoC 容器生命周期、Spring 事件发布、国际化等。

# Spring Bean 基础

## BeanDefinition

BeanDefinition 时 Spring Framework 中定义 Bean 配置元信息接口，包含：

1. Bean 的类名（必须是全限定类名）
2. Bean 行为配置元素，如作用域、自动绑定的模式、生命周期回调等
3. 其他 Bean 引用，又可称合作者（collaborators）或者依赖（dependencies）
4. 配置设置，比如 Bean 属性（Properties）

BeanDefinition 元信息

| 属性（Property）         | 说明                                          |
| ------------------------ | --------------------------------------------- |
| Class                    | Bean 全类名，必须是具体类，不能用抽象类或接口 |
| Name                     | Bean 的名称或者 ID                            |
| Scope                    | Bean 的作用域（如：singleton、prototype 等）  |
| Constructor arguments    | Bean 构造器参数（用于依赖注入）               |
| Properties               | Bean 属性设置（用于依赖注入）                 |
| Autowiring mode          | Bean 自动绑定模式（如：通过名称 byName）      |
| Lazy initialization mode | Bean 延迟初始化模式（延迟和非延迟）           |
| Initialization method    | Bean 初始化回调方法名称                       |
| Destruction method       | Bean 销毁回调方法名称                         |

BeanDefinition 的构建方式

1. 通过 BeanDefinitionBuilder
2. 通过 AbstactBeanDefinition 以及派生类

```java
/**
 * BeanDefinition构建示例
 */
public class BeanDefinitionCreationDemo {
    public static void main(String[] args) {
        // 1.通过BeanDefinitionBuilder
        BeanDefinitionBuilder beanDefinitionBuilder = BeanDefinitionBuilder.genericBeanDefinition(User.class);
        // 通过属性设置
        beanDefinitionBuilder.addPropertyValue("name","jyc");
        beanDefinitionBuilder.addPropertyValue("age","1");
        // 获取BeanDefinition实例
        AbstractBeanDefinition beanDefinition = beanDefinitionBuilder.getBeanDefinition();
        // BeanDefinition并非Bean的终态，可以自定义修改

        // 2.通过AbstactBeanDefinition以及派生类
        GenericBeanDefinition genericBeanDefinition = new GenericBeanDefinition();
        // 设置Bean类型
        genericBeanDefinition.setBeanClass(User.class);
        // 通过MutablePropertyValues批量操作属性
        MutablePropertyValues propertyValues = new MutablePropertyValues();
        propertyValues.addPropertyValue("id","1");
        propertyValues.addPropertyValue("name","jyc");
        genericBeanDefinition.setPropertyValues(propertyValues);
    }
}
```

## Spring Bean 命名

什么是 Bean 的名称？

每个 Bean 拥有一个或多个标识符（identifiers），这些标识符在 Bean 所在的容器必须是唯一的。通常，一个 Bean 仅有一个标识符，如果需要额外的，可考虑使用别名（Alias）来扩充。

在基于 XML 的配置元信息中，开发人员可用 id 或者 name 属性来规定 Bean 的标识符。通常 Bean 的标识符由字母组成，允许出现特殊字符，如果要想映入新的 Bean 的别名的话，可在 name 属性使用半角逗号（“,”）或分号（“;”）来间隔。

Bean 的 id 或 name 属性并非必须制定，如果留空的话，容器回味 Bean 自动生成一个唯一的名称。Bean 的名称尽管没有限制，不过官方建议采用驼峰的方式，更符合 Java 的命名约定。

Bean 名称生成器（BeanNameGenerator）主要有两种实现：

1. DefaultBeanNameGenerator（默认通用 BeanNameGenerator 实现）
2. AnnotationBeanNameGenerator

默认实现的核心代码：

```java
	public static String generateBeanName(
			BeanDefinition definition, BeanDefinitionRegistry registry, boolean isInnerBean)
			throws BeanDefinitionStoreException {

		String generatedBeanName = definition.getBeanClassName();
		if (generatedBeanName == null) {
			if (definition.getParentName() != null) {
				generatedBeanName = definition.getParentName() + "$child";
			}
			else if (definition.getFactoryBeanName() != null) {
				generatedBeanName = definition.getFactoryBeanName() + "$created";
			}
		}
		if (!StringUtils.hasText(generatedBeanName)) {
			throw new BeanDefinitionStoreException("Unnamed bean definition specifies neither " +
					"'class' nor 'parent' nor 'factory-bean' - can't generate bean name");
		}

		if (isInnerBean) {
			// Inner bean: generate identity hashcode suffix.
			return generatedBeanName + GENERATED_BEAN_NAME_SEPARATOR + ObjectUtils.getIdentityHexString(definition);
		}

		// Top-level bean: use plain class name with unique suffix if necessary.
		return uniqueBeanName(generatedBeanName, registry);
	}
```

如果是简单场景的 Bean 的名称：

```java
	public static String uniqueBeanName(String beanName, BeanDefinitionRegistry registry) {
		String id = beanName;
		int counter = -1;

		// Increase counter until the id is unique.
		String prefix = beanName + GENERATED_BEAN_NAME_SEPARATOR;
		while (counter == -1 || registry.containsBeanDefinition(id)) {
			counter++;
			id = prefix + counter;
		}
		return id;
	}
```

注解实现的核心源代码：

```java
@Override
	public String generateBeanName(BeanDefinition definition, BeanDefinitionRegistry registry) {
		if (definition instanceof AnnotatedBeanDefinition) {
			String beanName = determineBeanNameFromAnnotation((AnnotatedBeanDefinition) definition);
			if (StringUtils.hasText(beanName)) {
				// Explicit bean name found.
				return beanName;
			}
		}
		// Fallback: generate a unique default bean name.
		return buildDefaultBeanName(definition, registry);
	}
```

如果是一个普通的 Bean 就会调用 Java Beans 的 API：

```java
	protected String buildDefaultBeanName(BeanDefinition definition) {
		String beanClassName = definition.getBeanClassName();
		Assert.state(beanClassName != null, "No bean class name set");
		String shortClassName = ClassUtils.getShortName(beanClassName);
		return Introspector.decapitalize(shortClassName);
	}
```

Bean 别名（Alias）的价值：

1. 复用现有的 BeanDefinition

2. 更具有场景化的命名方法，比如：

   ```xml
   <alias name="myApp-dataSource" alias="subsystemA-datasource" />
   <alias name="myApp-dataSource" alias="subsystemB-datasource" />
   ```

## BeanDefinition 注册到 IoC 容器

BeanDefinition 注册的不同方式：

1. XML 配置元信息
   - <bean name ="..." ... />
2. Java 注解配置元信息
   - @Bean
   - @Component
   - @import
3. Java API 配置元信息
   - 命名方式：BeanDefinitionRegistry#registerBeanDefinition（String，BeanDefinition）
   - 非命名方式：BeanDefinitionReaderUtils#registerWithGeneratedName(AbstractBeanDefinition，BeanDefinitionRegistry)
   - 配置类方式：AnnotatedBeanDefinitionReader#register（Class）

通过 Java 注解配置元信息：

```java
/**
 * 注解BeanDefinition示例
 */
@Import(AnnotationBeanDefinitionDemo.Config.class) // 3.通过@Import方式导入
public class AnnotationBeanDefinitionDemo {

    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        // 注册配置类（configuration class）
        applicationContext.register(AnnotationBeanDefinitionDemo.class);
        applicationContext.refresh();
        System.out.println("Config类型的所有的Beans" + applicationContext.getBeansOfType(Config.class));
        System.out.println("user类型的所有的Beans" + applicationContext.getBeansOfType(User.class));
        applicationContext.close();
    }

    // 2.通过Component方式
    @Component //定义当前类作为Spring Bean（组件）
    public static class Config {
        // 1.通过@Bean方式定义
        @Bean({"user", "jyc"})
        public User user() {
            User user = new User();
            user.setId("1");
            user.setName("胡先森");
            return user;
        }
    }
}
```

Java API 配置元信息：

```java
/**
     * 命名Bean的注册方式
     *  @param registry
     * @param beanName
     */
    public static void registerUserBeanDefinition(BeanDefinitionRegistry registry, String beanName) {
        BeanDefinitionBuilder beanDefinitionBuilder = BeanDefinitionBuilder.genericBeanDefinition(User.class);
        beanDefinitionBuilder.addPropertyValue("id", "1").addPropertyValue("name", "jiyongchao");
        // 判断如果beanName参数存在时
        if (StringUtils.hasText(beanName)) {
            registry.registerBeanDefinition(beanName, beanDefinitionBuilder.getBeanDefinition());
        } else {
            // 非命名的Bean注册方法
            BeanDefinitionReaderUtils.registerWithGeneratedName(beanDefinitionBuilder.getBeanDefinition(), registry);
        }
    }
```

## 实例化 Bean 的方式

Bean 实例化：

1. 常规方式

   - 通过构造器（配置元信息：XML、Java 注解和 Java API）
   - 通过静态工厂方法（配置元信息：XML 和 Java API）
   - 通过 Bean 工厂方法（配置元信息：XML 和 Java API）
   - 通过 FactoryBean（配置元信息：XML、Java 注解和 Java API）

2. 特殊方式

   - 通过 ServiceLoaderFactoryBean（配置元信息：XML、Java 注解和 Java API）
   - 通过 AutowireCapableBeanFactory#createBean（java.lang.Class，int，boolean）
   - 通过 BeanDefinitionResgistry#registerBeanDefinition（String，BeanDefinition）

   常规方式实例化的示例：

   ```xml
   <beans xmlns="http://www.springframework.org/schema/beans"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

       <!--  静态方法实例化Bean  -->
       <bean id="user-by-static-method" class="org.jyc.thinking.in.spring.ioc.overview.dependency.domain.User" factory-method="createUser" />
       <!--  实例方法实例化Bean  -->
       <bean id="user-by-instance-method" factory-bean="userFactory" factory-method="createUser"/>
       <!--  Bean工厂实例化Bean  -->
       <bean id="userFactory" class="org.jyc.thinking.in.spring.bean.definition.factory.DefaultUserFactory" />
       <!--  FactoryBean实例化Bean  -->
       <bean id="user-by-factory-bean" class="org.jyc.thinking.in.spring.bean.definition.factory.UserFactoryBean"/>
   </beans>
   ```

   其中 UserFactoryBean 为：

   ```java
   /**
    * User Bean的FactoryBean的实现
    */
   public class UserFactoryBean implements FactoryBean {
       @Override
       public Object getObject() throws Exception {
           return new User();
       }

       @Override
       public Class<?> getObjectType() {
           return null;
       }
   }
   ```

   测试输出：

   ```java
   /**
    * Bean实例化示例
    */
   public class BeanInstantiationDemo {
       public static void main(String[] args) {
           BeanFactory beanFactory = new ClassPathXmlApplicationContext("classpath:/META-INF/bean-instantiation-context.xml");
           User user = beanFactory.getBean("user-by-static-method", User.class);
           User userByInstanceMethod = beanFactory.getBean("user-by-instance-method", User.class);
           User userByFactoryBean = beanFactory.getBean("user-by-instance-method", User.class);
           System.out.println(user);
           System.out.println(userByInstanceMethod);
           System.out.println(userByFactoryBean);

           System.out.println(user == userByInstanceMethod);
           System.out.println(user == userByFactoryBean);
       }
   }
   ```

   特殊方式的示例：

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <beans xmlns="http://www.springframework.org/schema/beans"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

       <bean id="userFactoryServiceLoader" class="org.springframework.beans.factory.serviceloader.ServiceLoaderFactoryBean" >
           <property name="serviceType" value="org.jyc.thinking.in.spring.bean.definition.factory.UserFactory" />
       </bean>
   </beans>
   ```

   测试输出：

   ```java
   public class SpecialBeanInstantiationDemo {
       public static void main(String[] args) {
           BeanFactory beanFactory = new ClassPathXmlApplicationContext("classpath:/META-INF/special-bean-instantiation-context.xml");
           ServiceLoader serviceLoader = beanFactory.getBean("userFactoryServiceLoader", ServiceLoader.class);
           displayServiceLoader(serviceLoader);
           demoServiceLoader();
       }
       public static void demoServiceLoader() {
           ServiceLoader<UserFactory> serviceLoader = ServiceLoader.load(UserFactory.class, Thread.currentThread().getContextClassLoader());
           displayServiceLoader(serviceLoader);
       }

       private static void displayServiceLoader(ServiceLoader<UserFactory> serviceLoader) {
           Iterator<UserFactory> iterator = serviceLoader.iterator();
           while (iterator.hasNext()) {
               UserFactory userFactory = iterator.next();
               System.out.println(userFactory.createUser());
           }
       }
   }
   ```

   通过 AutowireCapableBeanFactory 实例化：

   ```java
      public static void main(String[] args) {
           ApplicationContext applicationContext = new ClassPathXmlApplicationContext("classpath:/META-INF/special-bean-instantiation-context.xml");
           // 通过ApplicationContext获取AutowireCapableBeanFactory
           AutowireCapableBeanFactory beanFactory = applicationContext.getAutowireCapableBeanFactory();
           // 通过AutowireCapableBeanFactory创建UserFactory对象
           UserFactory userFactory = beanFactory.createBean(DefaultUserFactory.class);
           System.out.println(userFactory.createUser());
       }
   ```

   ## 初始化 Bean 的方式

   Bean 的初始化（Initialization）：

   1. @PostConstruct 标注方法
   2. 实现 InitializingBean 接口的 afterPropertiesSet()方法
   3. 自定义初始化方法
      - XML 配置：<bean init-method="init" ... />
      - Java 注解：@Bean(initMethod="init")
      - Java API：AbstractBeanDefinition#setInitMethodName(String)

初始化的示例：

```java
public class DefaultUserFactory implements UserFactory, InitializingBean {
    // 1.基于@PostConstruct注解
    @PostConstruct
    public void init() {
        System.out.println("@PostConstruct: UserFactory 初始化中....");
    }

    @Override
    public void afterPropertiesSet() throws Exception {
        System.out.println("afterPropertiesSet: UserFactory 初始化中....");
    }

    public void initUserFactory() {
        System.out.println("自定义初始化方法： initUserFactory： UserFactory 初始化中....");
    }
}
```

调用的结果：

```java
@Configuration
public class BeanInitializationDemo {
    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(BeanInitializationDemo.class);
        applicationContext.refresh();
        UserFactory userFactory = applicationContext.getBean(UserFactory.class);
        applicationContext.close();

    }

    @Bean(initMethod = "initUserFactory")
    public UserFactory userFactory() {
        return new DefaultUserFactory();
    }
}
```

最终实际上都会调用的 AbstractBeanDefinition 的 setInitMethodName

```java
	public void setInitMethodName(@Nullable String initMethodName) {
		this.initMethodName = initMethodName;
	}
```

三者的执行顺序：

```java
@PostConstruct: UserFactory 初始化中....
afterPropertiesSet: UserFactory 初始化中....
自定义初始化方法： initUserFactory： UserFactory 初始化中....
```

## 延迟初始化 Bean

Bean 延迟初始化（Lazy Initialization）

1. XML 配置：<bean lazy-init="true" .../>
2. Java 注解：@Lazy(true)

Spring 容器返回的对象和非延迟的对象存在怎样的差异？

非延迟初始化在 Spring 应用上下文启动完成后，被初始化。而延迟初始化是在依赖查找和依赖注入的时候才会进行初始化。

## 销毁 Bean

Bean 销毁（Destroy）

1. @PreDestory 标注方法
2. 实现 DisposableBean 接口的 destory()方法
3. 自定义销毁方法
   - XML 配置：<bean destory="destory" .../>
   - Java 注解：@Bean(destory="destory")
   - Java API: AbstractBeanDefinition#setDestoryMethodName(String)

销毁的示例：

```java
public class DefaultUserFactory implements UserFactory, DisposableBean {

    @PreDestroy
    public void preDestory() {
        System.out.println("@PreDestroy: UserFactory 销毁中....");
    }

    @Override
    public void destroy() throws Exception {
        System.out.println("DisposableBean#destroy: UserFactory 销毁中....");
    }

    public void doDestory() {
        System.out.println("自定义销毁方法：doDestory()： UserFactory 销毁中....");
    }
}
```

调用的结果：

```java
public class BeanDestoryDemo {
    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(BeanDestoryDemo.class);
        applicationContext.refresh();
        // 非延迟初始化在Spring应用上下文启动完成后，被初始化。
        System.out.println("应用上下文已启动...");
        UserFactory userFactory = applicationContext.getBean(UserFactory.class);
        System.out.println(userFactory);
        System.out.println("应用上下文准备关闭...");
        applicationContext.close();
        System.out.println("应用上下文已关闭...");
    }

    @Bean(destroyMethod = "doDestory")
    public UserFactory userFactory() {
        return new DefaultUserFactory();
    }
}

```

通过不同时机的打印，可以观察到 Bean 的销毁的时机就是在应用上下文关闭的时候。

三者不同方式的执行结果：

```java
应用上下文已启动...
应用上下文准备关闭...
@PreDestroy: UserFactory 销毁中....
DisposableBean#destroy: UserFactory 销毁中....
自定义销毁方法：doDestory()： UserFactory 销毁中....
应用上下文已关闭...
```

## 垃圾回收 Spring Bean

Bean 垃圾回收（GC）

1. 关闭 Spring 容器（应用上下文）
2. 执行 GC
3. Spring Bean 覆盖的 finalize()方法被回调

```java
/**
 * Bena垃圾回收的示例
 */
public class BeanGarbageCollectionDemo {
    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(BeanInitializationDemo.class);
        applicationContext.refresh();
        applicationContext.close();
        System.out.println("Spring 应用上下文已关闭");
        // 强制触发GC
        System.gc();
    }
}
```

这里我们重写了 DefaultUserFactory 中的 finalize()方法：

```java
    @Override
    protected void finalize() throws Throwable {
        System.out.println("当前DefaultUserFactory 对象正在被垃圾回收");
    }
```

## 面试题

### 如何注册一个 Spring Bean？

通过 BeanDefinition 和外部单体对象来注册。

```java
/**
 * 单体Bean注册示例
 */
public class SingletonBeanRegistrationDemo {
    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        // 注册外部单例对象
        UserFactory userFactory = new DefaultUserFactory();
        // 创建一个外部UserFactory对象
        ConfigurableListableBeanFactory beanFactory = applicationContext.getBeanFactory();
        // 注册外部单例对象
        beanFactory.registerSingleton("userFactory", userFactory);
        applicationContext.refresh();
        UserFactory userFactoryByLookup = beanFactory.getBean("userFactory", UserFactory.class);
        System.out.println("userFactory == userFactoryByLookup: " + (userFactory == userFactoryByLookup));
        applicationContext.close();
    }
}
```

### 什么是 Spring BeanDefinition？

BeanDefinition 是关于 Bean 定义的元信息的接口，允许我们通过 getter、setter 方法方式来进行存储信息。

### Spring 容器是怎样管理注册 Bean

如 IoC 配置元信息读取和解析、依赖查找和注入以及 Bean 生命周期等。

# 依赖查找

## 依赖查找简介

1. 单一类型依赖查找
   - JNDI - javax.naming.Context#lookup(javax.naming.Name)
   - JavaBeans - java.beans.beancontext.BeanContext
2. 集合类型依赖查找
   - java.beans.beancontext.BeanContext
3. 层次性依赖查找
   - java.beans.beancontext.BeanContext

## 单一类型依赖查找

单一类型依赖查找接口-BeanFactory

1. 根据 Bean 名称查找
   - getBean(String)
   - Spring 2.5 覆盖默认参数：getBean(String,Object...)
2. 根据 Bean 类型查找
   - Bean 实时查找
     - Spring 3.0 getBean(Class)
     - Spring 4.1 覆盖默认参数：getBean(Class,Object...)
   - Spring 5.1 Bean 延迟查找
     - getBeanProvider(Class)
     - getBeanProvider(ResolvableType)
3. 根据 Bean 名称 + 类型查找：getBean(String,Class)

利用 ObejctProvider 进行依赖查找：

```java
/**
 * 通过ObjectProvider进行依赖查找
 */
public class ObejctProviderDemo { // @Configuration是非必须的注解
    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(ObejctProviderDemo.class);
        applicationContext.refresh();
        lookupByObejctProvider(applicationContext);
        applicationContext.close();
    }

    @Bean
    public String helloworld() { // 方法名就是Bean名称 = “helloworld”
        return "helloworld";
    }

    private static void lookupByObejctProvider(AnnotationConfigApplicationContext applicationContext) {
        ObjectProvider<String> beanProvider = applicationContext.getBeanProvider(String.class);
        System.out.println(beanProvider.getObject());
    }
}
```

## 集合类型依赖查找

集合类型依赖查找接口-ListableBeanFactory

1. 根据 Bean 类型查找
   - 根据同类型 Bean 名称列表
     - getBeanNamesForType（Class）
     - Spring 4.2 getBeanNamesForType（ResolvableType）
   - 获取同类型 Bean 实例列表
     - getBeanOfType（Class）以及重载方法
2. 通过注解类型查找
   - Spring 3.0 获取标注类型 Bean 名称列表
     - getBeanNamesForAnnotation（Class<? extends Annotation>）
   - Spring 3.0 获取标注类型 Bean 实例列表
     - getBeansWithAnnotation（Class<? extends Annotation>）
   - Spring 3.0 获取指定名称 + 标注类型 Bean 实例

相关的示例实际上在之前就已经提到过了：

```java
  /**
     * 通过注解查找
     * @param beanFactory
     */
    private static void lookupByAnnotationType(BeanFactory beanFactory) {
        if (beanFactory instanceof ListableBeanFactory) {
            ListableBeanFactory listableBeanFactory = (ListableBeanFactory) beanFactory;
            Map<String, User> users = (Map)listableBeanFactory.getBeansWithAnnotation(Super.class);
            System.out.println("查找到的所有标注@Super的User集合对象：" + users);
        }
    }

    /**
     * 按照类型查找集合对象
     * @param beanFactory
     */
    private static void lookupCollectionType(BeanFactory beanFactory) {
        if (beanFactory instanceof ListableBeanFactory) {
            ListableBeanFactory listableBeanFactory = (ListableBeanFactory) beanFactory;
            Map<String, User> users = listableBeanFactory.getBeansOfType(User.class);
            System.out.println("查找到的所有的User集合对象：" + users);
        }
    }
```

## 层次性依赖查找

层次性依赖查找接口-HierachicalBeanFactory

1. 双亲 BeanFactory：getParentBeanFacotry
2. 层次性查找：
   - 根据 Bean 名称查找
     - 基于 containsLocalBean 方法实现
   - 根据 Bean 类型查找实例列表
     - 单一类型：BeanFactoryUtils#beanOfType
     - 集合类型 BeanFactoryUtils#beanOfTypeIncludingAncestors
   - 根据 Java 注解查找名称列表
     - BeanFactoryUtils#beanNamesForTypeIncludingAncestors

## 延迟依赖查找

Bean 延迟依赖查找接口

1. org.springframework.beans.factory.ObjectFactory
2. org.springframwork.beans.factory.ObjecyProvider
   - Spring 5 对 Java8 特性扩展
     - 函数式接口
       - getIfAvailable(Supplier)
       - ifAvailable(Consumer)
     - Stream 扩展-stream()

相关示例：

```java
public class ObejctProviderDemo { // @Configuration是非必须的注解
    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(ObejctProviderDemo.class);
        applicationContext.refresh();
        lookupByObejctProvider(applicationContext);
        lookupIfAvailable(applicationContext);
        lookupByStreamOps(applicationContext);
        applicationContext.close();
    }

    private static void lookupByStreamOps(AnnotationConfigApplicationContext applicationContext) {
        ObjectProvider<String> beanProvider = applicationContext.getBeanProvider(String.class);
//        Iterable<String> stringIterable = beanProvider;
//        for (String string : stringIterable) {
//            System.out.println(string);
//        }
        beanProvider.stream().forEach(System.out::println);
    }

    private static void lookupIfAvailable(AnnotationConfigApplicationContext applicationContext) {
        // User对象并不存在
        ObjectProvider<User> userObjectProvider = applicationContext.getBeanProvider(User.class);
        User user = userObjectProvider.getIfAvailable(User::createUser);
        System.out.println("当前User对象: " + user);

    }

    @Bean
    @Primary
    public String helloworld() {
        return "helloworld";
    }

    @Bean
    public String message() {
        return "Message";
    }

    private static void lookupByObejctProvider(AnnotationConfigApplicationContext applicationContext) {
        ObjectProvider<String> beanProvider = applicationContext.getBeanProvider(String.class);
        System.out.println(beanProvider.getObject());
    }
}
```

## 安全依赖查找

安全性指的是没有查找到 Bean 的时候，是否会抛出异常。有关依赖查找安全性对比如下

| 依赖查找类型 | 代表实现                           | 是否安全 |
| ------------ | ---------------------------------- | -------- |
| 单一类型查找 | BeanFactory#getBean                | 否       |
|              | ObjectFactory#getObject            | 否       |
|              | ObjectProvider#getIfAvailable      | 是       |
|              |                                    | 是       |
| 集合类型查找 | ListableBeanFactory#getBeansOfType | 是       |
|              | ObjectProvider#stream              | 是       |

注意：层次性依赖查找的安全性取决于其扩展的单一或集合类型的 BeanFactory 接口。

类型安全的依赖查找的相关示例：

```java
/**
 * 类型安全的依赖查找示例
 */
public class TypeSafetyDependencyLookupDemp {
    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(TypeSafetyDependencyLookupDemp.class);
        applicationContext.refresh();
        // 演示BeanFactory#getBean方法的安全性
        displayBeanFactoryGetBean(applicationContext);
        // 演示ObjectFactory#getObject方法的安全性
        displayBeanFactoryGetObject(applicationContext);
        // 演示ObjectProvider#ifAvailable方法的安全性
        displayObjectProviderIfAvailable(applicationContext);
        // 演示ListableBeanFactory#getBeansOfTYpe方法的安全性
        displayListableBeanFactoryGetBeansType(applicationContext);
        // 演示ObjectProvider#stream方法的安全性
        displayObjectProviderStreamOps(applicationContext);
        applicationContext.close();
    }

    private static void displayObjectProviderStreamOps(AnnotationConfigApplicationContext applicationContext) {
        ObjectProvider<User> userObjectProvider = applicationContext.getBeanProvider(User.class);
        printBeansException("displayObjectProviderStreamOps", () -> userObjectProvider.stream().forEach(System.out::println));
    }

    private static void displayListableBeanFactoryGetBeansType(ListableBeanFactory beanFactory) {
        printBeansException("displayListableBeanFactoryGetBeansType",() -> beanFactory.getBeanNamesForType(User.class));
    }

    private static void displayObjectProviderIfAvailable(AnnotationConfigApplicationContext applicationContext) {
        ObjectProvider<User> objectProvider = applicationContext.getBeanProvider(User.class);
        printBeansException("displayObjectProviderIfAvailable", objectProvider::getIfAvailable);
    }

    private static void displayBeanFactoryGetObject(AnnotationConfigApplicationContext applicationContext) {
        // ObjectProvider is ObjectFactory
        ObjectFactory<User> userObjectFactory = applicationContext.getBeanProvider(User.class);
        printBeansException("displayBeanFactoryGetObject", userObjectFactory::getObject);
    }

    public static void displayBeanFactoryGetBean(BeanFactory beanFactory) {
        printBeansException("displayBeanFactoryGetBean", () -> beanFactory.getBean(User.class));
    }

    private static void printBeansException(String source, Runnable runnable) {
        System.err.println("Source from: " + source);
        System.err.println("============================");
        try {
            runnable.run();
        } catch (BeansException exception) {
            exception.printStackTrace();
        }
    }
}
```

## 内建可查找的依赖

AbastractApplicationContext 内建可查找的依赖：

| Bean 名称                   | Bena 实例                        | 使用场景                |
| --------------------------- | -------------------------------- | ----------------------- |
| environment                 | Environment 对象                 | 外部化配置以及 Profiles |
| systemProperties            | java.util.Properties 对象        | Java 系统属性           |
| systemEnvironment           | java.util.Map 对象               | 操作系统环境变量        |
| messageSource               | MessageSource 对象               | 国际化文案              |
| lifecycleProcessor          | lifecycleProcessor 对象          | Lifecycle Bean 处理器   |
| applicationEventMulticaster | ApplicationEventMulticaster 对象 | Spring 事件广播器       |

注解驱动 Spring 应用上下文内建可查找的依赖（部分）：

| Bean 名称                                                                  | Bean 实例                                 | 使用场景                                              |
| -------------------------------------------------------------------------- | ----------------------------------------- | ----------------------------------------------------- |
| org.springframework.context.event.internalConfigurationAnnotationProcessor | ConfigurationClassPostProcessor 对象      | 处理 Spring 配置类                                    |
| org.springframework.context.event.internalAutowiredAnnotationProcessor     | AutowiredAnnotationBeanPostProcessor 对象 | 处理@Autowired 以及@Value 注解                        |
| org.springframework.context.event.internalCommonAnnotationProcessor        | CommonAnnotationBeanPostProcessor 对象    | （条件激活）处理 JSR-250 注解，如@PostConstruct 等    |
| org.springframework.context.event.internalEventListenerProcessor           | EventListenerMethodProcessor 对象         | 处理标注@EventListener 的 Spring 事件监听方法         |
| org.springframework.context.event.internalListenerFactory                  | DefaultEventListenerFactory 对象          | @EventListener 事件监听方法适配为 ApplicationListener |
| org.springframework.context.event.internalPersistenceAnnotationProcessor   | PersistenceAnnotationProcessor 对象       | 条件激活处理 JPA 注解场景                             |

这些内建的 Bean 的初始化都是在 AnnotationConfigUtils 中完成的。

## 依赖查找中典型异常

BeansException 子类型

| 异常类型                        | 触发条件（举例）                       | 场景举例                                         |
| ------------------------------- | -------------------------------------- | ------------------------------------------------ |
| NoSuchBeanDefinitionException   | 当查找 Bean 不存在于 IoC 容器时        | BeanFactory#getBean<br />ObjectFactory#getObject |
| NoUniqueBeanDefinitionException | 类型查找时，IoC 容器存在多个 Bean 实例 | BeanFactory#getBean(Class)                       |
| BeanInstantiationException      | 当 Bean 所对应的类型非具体类时         | BeanFactory#getBean                              |
| BeanCreationException           | 当 Bean 初始化过程中                   | Bean 初始化方法执行异常时                        |
| BeanDefinitionStoreException    | 当 BeanDefinition 配置元信息非法时     | XML 配置资源无法打开时                           |

NoUniqueBeanDefinitionException 示例：

```java
/**
 * NoUniqueBeanDefinitionException示例
 */
public class NoUniqueBeanDefinitionExceptionDemo {
    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(NoUniqueBeanDefinitionExceptionDemo.class);
        applicationContext.refresh();
        try {
            applicationContext.getBean(String.class);
        } catch (NoUniqueBeanDefinitionException e) {
            System.err.printf("Spring应用上下文存在%d 个 %s 类型的Bean,具体原因: %s%n", e.getNumberOfBeansFound(),
                    String.class.getName(), e.getMessage());
        }
        applicationContext.close();
    }

    @Bean
    public String bean1() {
        return "bean1";
    }

    @Bean
    public String bean2() {
        return "bean2";
    }

    @Bean
    public String bean3() {
        return "bean3";
    }
}
```

BeanInstantiationException 示例：

```java
/**
 * BeanInstantiationException示例
 */
public class BeanInstantiationExceptionDemo {
    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        // 注册BeanDefinition
        BeanDefinitionBuilder beanDefinitionBuilder = BeanDefinitionBuilder.genericBeanDefinition(CharSequence.class);
        // CharSequence是一个接口，所以实例化的时候会报错
        applicationContext.registerBeanDefinition("errorBean", beanDefinitionBuilder.getBeanDefinition());
        applicationContext.refresh();
        applicationContext.close();
    }
}
```

BeanCreationException 示例：

```java
/**
 * BeanCreationException示例
 */
public class BeanCreationExceptionDemo {
    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        // 注册BeanDefinition
        BeanDefinitionBuilder beanDefinitionBuilder = BeanDefinitionBuilder.genericBeanDefinition(POJO.class);
        applicationContext.registerBeanDefinition("errorBean", beanDefinitionBuilder.getBeanDefinition());
        applicationContext.refresh();
        applicationContext.close();
    }

    static class POJO implements InitializingBean {

        @Bean
        public void init() throws Throwable{
            throw new Throwable("init(): For purposers...");
        }

        @Override
        public void afterPropertiesSet() throws Exception {
            throw new Exception("afterPropertiesSet(): For purposes...");
        }
    }
}
```

## 面试题

### ObjectFactory 与 BeanFactory 的区别

ObjectFactory 与 BeanFactory 均提供依赖查找的能力，不过 ObjectFactory 仅关注一个或一种类型的 Bean 依赖查找，并且自身不具备依赖查找的能力，能力由 BeanFactory 输出。

BeanFactory 则提供了单一类型、集合类型以及层次性等多种依赖查找方式。

### BeanFactory.getBean 操作是否线程安全？

BeanFactory.getBean 方法的执行是线程安全的，操作过程中会增加互斥锁。

### Spring 的依赖查找和依赖注入在来源上有什么区别？

待定...

# 依赖注入

## 依赖注入的模式和类型

1. 手动模式-配置或者编程的方式，提前安排注入规则
   - XML 资源配置元信息
   - Java 注解配置元信息
   - API 配置元信息
2. 自动模式-实现方提供依赖自动关联的方式，按照内建的注入规则
   - Autowring(自动绑定)

依赖注入类型：

| 依赖注入类型 | 配置元数据举例                                    |
| ------------ | ------------------------------------------------- |
| Setter 方法  | <proepty name="user" ref="userBean" />            |
| 构造器       | <constructor-arg name="user" ref="userBean" />    |
| 字段         | @Autowired<br />User user;                        |
| 方法         | @Autowired<br />public void user(User user) {...} |
| 接口回调     | class MyBean implements BeanFactoryAware{...}     |

## 自动绑定

Autowiring modes:

| 模式        | 说明                                                                 |
| ----------- | -------------------------------------------------------------------- |
| no          | 默认值，未激活 Autowiring，需要手动指定依赖注入对象                  |
| byName      | 根据被注入属性的名称作为 Bean 名称进行依赖查找，并将对象设置到该属性 |
| byType      | 根据被注入属性的类型作为依赖类型进行查找，并将对象设置到该属性       |
| constructor | 特殊 byType 类型，用于构造器参数                                     |

可以参考：org.springframework.beans.factory.annotation.Autowire。

```java
public enum Autowire {

	/**
	 * Constant that indicates no autowiring at all.
	 */
	NO(AutowireCapableBeanFactory.AUTOWIRE_NO),

	/**
	 * Constant that indicates autowiring bean properties by name.
	 */
	BY_NAME(AutowireCapableBeanFactory.AUTOWIRE_BY_NAME),

	/**
	 * Constant that indicates autowiring bean properties by type.
	 */
	BY_TYPE(AutowireCapableBeanFactory.AUTOWIRE_BY_TYPE);


	private final int value;


	Autowire(int value) {
		this.value = value;
	}

	public int value() {
		return this.value;
	}

	/**
	 * Return whether this represents an actual autowiring value.
	 * @return whether actual autowiring was specified
	 * (either BY_NAME or BY_TYPE)
	 */
	public boolean isAutowire() {
		return (this == BY_NAME || this == BY_TYPE);
	}

}
```

自动绑定的不足之处：

1. 构造器参数以及 property 上面的设置通常会覆盖掉 Autowiring，也不能绑定一些简单的类型，比如 String、Classes、properties
2. Autowiring 无法把控注入的时候的精确性，会导致一些不确定的情况发生。
3. wiring 很难在工具上产生一些文档或者相关提示。
4. 如果应用上下文中存在多个 Bean 的定义，会发生歧义性，可能会抛出 NoUniqueBeanDefinitionException。

## Setter 注入

Setter 注入实现方法：

1. 手动模式：
   - XML 资源配置元信息
   - Java 注解配置元信息
   - API 配置元信息
2. 自动模式
   - byName
   - byType

这里我们新建一个 UserHolder：

```java
/**
 * {@link User} 的holder类
 */
public class UserHolder {

    public UserHolder() {

    }

    public UserHolder(User user) {
        this.user = user;
    }

    private User user;

    public User getUser() {
        return user;
    }

    public void setUser(User user) {
        this.user = user;
    }

    @Override
    public String toString() {
        return "UserHolder{" +
                "user=" + user +
                '}';
    }
}
```

通过 XML 的方式注入：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <import resource="classpath:/META-INF/dependency-lookup-context.xml" />

    <bean class="org.jyc.thinking.in.spring.ioc.dependcy.injection.UserHolder">
        <property name="user" ref="user" />
    </bean>
</beans>
```

通过 XML 的方式注入演示的示例：

```java
/**
 * 基于XML资源的依赖，Setter方法注入依赖
 */
public class XmlDependencySetterInjectionDemo {
    public static void main(String[] args) {
        DefaultListableBeanFactory beanFactory = new DefaultListableBeanFactory();
        XmlBeanDefinitionReader beanDefinitionReader = new XmlBeanDefinitionReader(beanFactory);

        String xmlResourcePath = "classpath:/MTEA-INF/dependency-setter-injection.xml";
        // 加载XML资源，解析并且生成BeanDefinition
        beanDefinitionReader.loadBeanDefinitions(xmlResourcePath);
        //依赖查找并且创建Bean
        UserHolder userHolder = beanFactory.getBean(UserHolder.class);
        System.out.println(userHolder);
    }
}

```

基于注解的依赖注入的演示示例：

```java
/**
 * 基于注解的Setter方法注入依赖
 */
public class AnnotationDependencySetterInjectionDemo {
    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(AnnotationDependencySetterInjectionDemo.class);
        applicationContext.refresh();

        XmlBeanDefinitionReader beanDefinitionReader = new XmlBeanDefinitionReader(applicationContext);
        String xmlResourcePath = "classpath:/MTEA-INF/dependency-lookup-context.xml";
        beanDefinitionReader.loadBeanDefinitions(xmlResourcePath);

        UserHolder userHolder = applicationContext.getBean(UserHolder.class);
        System.out.println(userHolder);
        applicationContext.close();
    }

    @Bean
    public UserHolder userHolder(User user) {
        UserHolder userHolder = new UserHolder();
        userHolder.setUser(user);
        return userHolder;
    }
}
```

基于 Api 的依赖注入的演示：

```java
/**
 * 基于API的Setter方法注入依赖
 */
public class ApiDependencySetterInjectionDemo {
    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        BeanDefinition userBeanDefinition = createUserBeanDefinition();
        // 注册UserHolder的BeanDefinition
        applicationContext.registerBeanDefinition("UserHolder",userBeanDefinition);
        applicationContext.refresh();
        XmlBeanDefinitionReader beanDefinitionReader = new XmlBeanDefinitionReader(applicationContext);
        String xmlResourcePath = "classpath:/MTEA-INF/dependency-lookup-context.xml";
        beanDefinitionReader.loadBeanDefinitions(xmlResourcePath);

        UserHolder userHolder = applicationContext.getBean(UserHolder.class);
        System.out.println(userHolder);
        applicationContext.close();
    }

    /**
     * 为{@link UserHolder} 生成{@link BeanDefinition}
     * @return
     */
    public static BeanDefinition createUserBeanDefinition() {
        BeanDefinitionBuilder beanDefinitionBuilder = BeanDefinitionBuilder.genericBeanDefinition(UserHolder.class);
        beanDefinitionBuilder.addPropertyReference("user","SuperUser");
        return beanDefinitionBuilder.getBeanDefinition();
    }
}
```

自动配置的主要应用场景在 XML 文件当中：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <import resource="classpath:/META-INF/dependency-lookup-context.xml" />
	<!--这里可以通过byType或者byName进行注入-->
    <bean class="org.jyc.thinking.in.spring.ioc.dependcy.injection.UserHolder" autowire="byType">
	<!--        <property name="user" ref="user" />-->
    </bean>
</beans>
```

## 构造器注入

构造器注入的实现方法：

1. 手动模式
   - XML 资源配置元信息
   - Java 注解配置元信息
   - API 配置元信息
2. 自动模式
   - constructor

XML 资源配置的方式：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <import resource="classpath:/META-INF/dependency-lookup-context.xml" />

    <bean class="org.jyc.thinking.in.spring.ioc.dependcy.injection.UserHolder">
        <constructor-arg name="user" ref="SuperUser" />
    </bean>
</beans>
```

XML 资源配置方式的示例：

```java
/**
 * 基于XML资源的依赖，构造器注入依赖
 */
public class XmlDependencyConstructorInjectionDemo {
    public static void main(String[] args) {
        DefaultListableBeanFactory beanFactory = new DefaultListableBeanFactory();
        XmlBeanDefinitionReader beanDefinitionReader = new XmlBeanDefinitionReader(beanFactory);

        String xmlResourcePath = "classpath:/META-INF/dependency-constructor-injection.xml";
        // 加载XML资源，解析并且生成BeanDefinition
        beanDefinitionReader.loadBeanDefinitions(xmlResourcePath);
        //依赖查找并且创建Bean
        UserHolder userHolder = beanFactory.getBean(UserHolder.class);
        System.out.println(userHolder);
    }
}
```

Java 注解方式的核心部分：

```java
    @Bean
    public UserHolder userHolder(User user) {
        return new UserHolder(user);
    }
```

API 配置元信息的方式的核心部分：

```java
    /**
     * 为{@link UserHolder} 生成{@link BeanDefinition}
     * @return
     */
    public static BeanDefinition createUserBeanDefinition() {
        BeanDefinitionBuilder beanDefinitionBuilder = BeanDefinitionBuilder.genericBeanDefinition(UserHolder.class);
        beanDefinitionBuilder.addConstructorArgReference("SuperUser");
        return beanDefinitionBuilder.getBeanDefinition();
    }
```

构造器自动绑定的示例：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <import resource="classpath:/META-INF/dependency-lookup-context.xml" />

    <bean class="org.jyc.thinking.in.spring.ioc.dependcy.injection.UserHolder" autowire="constructor" />
</beans>
```

## 字段注入

实现方法：

1. 手动模式
   - @Autowird
   - @Resource
   - @inject（可选）

字段注入的示例：

```java
/**
 * 基于注解的字段注入依赖
 */
public class AnnotationDependencyFiledInjectionDemo {

    @Autowired
    private
    //static @Autowired会忽略掉静态字段
    UserHolder userHolder;

    @Resource
    private UserHolder userHolder2;

    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        // 配置Class也是 Spring Bean
        applicationContext.register(AnnotationDependencyFiledInjectionDemo.class);
        applicationContext.refresh();

        XmlBeanDefinitionReader beanDefinitionReader = new XmlBeanDefinitionReader(applicationContext);
        String xmlResourcePath = "classpath:/META-INF/dependency-lookup-context.xml";
        beanDefinitionReader.loadBeanDefinitions(xmlResourcePath);

        AnnotationDependencyFiledInjectionDemo demo = applicationContext.getBean(AnnotationDependencyFiledInjectionDemo.class);

        // Autowired字段关联
        UserHolder userHolder = demo.userHolder;
        // @Resource
        UserHolder userHolder2 = demo.userHolder2;
        System.out.println(userHolder);
        System.out.println(userHolder2);

        System.out.println(userHolder == userHolder2);
        applicationContext.close();
    }

    @Bean
    public UserHolder userHolder(User user) {
        return new UserHolder(user);
    }
}
```

## 方法注入

1. 手动模式
   - @Autowird
   - @Resource
   - @inject（可选）
   - @Bean

方法注入的示例：

```java

    private UserHolder userHolder;

    private UserHolder userHolder2;

    @Autowired
    public void initUserHolder(UserHolder userHolder) {
        this.userHolder = userHolder;
    }

    @Resource
    public void initUserHolder2(UserHolder userHolder2) {
        this.userHolder2 = userHolder2;
    }

    @Bean
    public UserHolder userHolder(User user) {
        return new UserHolder(user);
    }
```

## 接口回调注入

Aware 系列接口回调

1. 自动模式

   | 内建接口                       | 说明                                                     |
   | ------------------------------ | -------------------------------------------------------- |
   | BeanFactoryAware               | 获取 IoC 容器-BeanFactory                                |
   | ApplicationContextAware        | 获取 Spring 应用上下文-ApplicationConetxt 对象           |
   | EnvironmentAware               | 获取 Environment 对象                                    |
   | ResourceLoaderAware            | 获取资源加载器对象-ResourceLoader                        |
   | BeanClassLoaderAware           | 获取加载当前 Bean Class 的 ClassLoader                   |
   | BeanNameAware                  | 获取当前 Bean 名称                                       |
   | MessageSourceAware             | 获取 MessageSource 对象，用于 Spring 国际化              |
   | ApplicationEventPublisherAware | 获取 ApplicationEventPublishAware 对象，用于 Spring 事件 |
   | EmbeddedValueResolverAware     | 获取 StringValueResolver 对象，用占位符处理              |

   接口回调示例：

   ```java
   /**
    * 基于{@link org.springframework.beans.factory.Aware} 接口回调的示例
    */
   public class AwareInterfaceDependencyInjectionDemo implements BeanFactoryAware, ApplicationContextAware {

       private static BeanFactory beanFactory;

       private static ApplicationContext applicationContext;

       @Override
       public void setApplicationContext(ApplicationContext applicationContext) throws BeansException {
           AwareInterfaceDependencyInjectionDemo.applicationContext = applicationContext;
       }

       @Override
       public void setBeanFactory(BeanFactory beanFactory) throws BeansException {
           AwareInterfaceDependencyInjectionDemo.beanFactory = beanFactory;
       }

       public static void main(String[] args) {
           AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext();
           context.register(AwareInterfaceDependencyInjectionDemo.class);
           context.refresh();

           System.out.println(beanFactory == context.getBeanFactory());
           System.out.println(applicationContext == context);
           context.close();
       }
   }
   ```

## 依赖注入类型选择

注入选型

1. 低依赖：构造器注入
2. 多以来：Setter 方法注入
3. 便利性：字段注入
4. 声明类：方法注入

## 基础类型注入

基础类型

1. 原生类型（Primitive）：boolean、byte、char、short、int、float、long、double
2. 标量类型（Scalar）：Number、Character、Boolean、Enum、Locale、Charset、Currency、Properties、UUID
3. 常规类型（General）：Object、String、TimeZone、Calendar、Optional 等
4. Spring 类型：Resource、InputSource、Formatter 等。

## 集合类型注入

集合类型

1. 数组类型（Array）：原生类型、标量类型、常规类型、Spring 类型
2. 集合类型（Collection）
   - Collection：List、Set（SortedSet、NavigableSet、EnumSet）
   - Map：Properties

## 限定注入

1. 使用注解@Qualifier 限定
   - 通过 Bean 名称限定
   - 通过分组限定
2. 基于注解@Qualifier 扩展限定
   - 自定义注解，如 Spring Cloud @LoadBalanced

使用注解@Qualifer 限定 Bean 的名称的示例：

```java
/**
 * {@link org.springframework.beans.factory.annotation.Qualifier} 使用示例
 */
public class QualifierAnnotationDependencyInjectionDemo {

    @Autowired // SuperUser -> primary = true
    private User user;

    @Autowired
    @Qualifier("user") // 指定Bean名称或者ID
    private User namedUser;

    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(QualifierAnnotationDependencyInjectionDemo.class);
        applicationContext.refresh();
        XmlBeanDefinitionReader beanDefinitionReader = new XmlBeanDefinitionReader(applicationContext);
        String xmlResourcePath = "classpath:/META-INF/dependency-lookup-context.xml";
        beanDefinitionReader.loadBeanDefinitions(xmlResourcePath);
        QualifierAnnotationDependencyInjectionDemo demo = applicationContext.getBean(QualifierAnnotationDependencyInjectionDemo.class);
        System.out.println("demo.user = " + demo.user);
        System.out.println("demo.namedUser = " + demo.namedUser);
        applicationContext.close();
    }
}
```

还可以使用@Qulifier 对注入的 Bean 可以进行逻辑上的分组：

```java
/**
 * {@link org.springframework.beans.factory.annotation.Qualifier} 使用示例
 */
public class QualifierAnnotationDependencyInjectionDemo {

    @Autowired // SuperUser -> primary = true
    private User user;

    @Autowired
    @Qualifier("user") // 指定Bean名称或者ID
    private User namedUser;

    @Autowired
    private Collection<User> allUsers;

    @Autowired
    @Qualifier
    private Collection<User> qualifierUsers;

    @Bean
    @Qualifier // 进行逻辑分组
    public User user1() {
        User user = new User();
        user.setId("7");
        return user;
    }

    @Bean
    @Qualifier
    public User user2() {
        User user = new User();
        user.setId("8");
        return user;
    }

    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(QualifierAnnotationDependencyInjectionDemo.class);
        applicationContext.refresh();
        XmlBeanDefinitionReader beanDefinitionReader = new XmlBeanDefinitionReader(applicationContext);
        String xmlResourcePath = "classpath:/META-INF/dependency-lookup-context.xml";
        beanDefinitionReader.loadBeanDefinitions(xmlResourcePath);
        QualifierAnnotationDependencyInjectionDemo demo = applicationContext.getBean(QualifierAnnotationDependencyInjectionDemo.class);
        // 输出SuperUSer Bean
        System.out.println("demo.user = " + demo.user);
        // 输出 user Bean
        System.out.println("demo.namedUser = " + demo.namedUser);
        // 输出 SuperUSer、user,注意这里输出的不是所有的user对象
        System.out.println("demo.allUsers = " + demo.allUsers);
        // 输出 user1、user2
        System.out.println("demo.qualifierUsers = " + demo.qualifierUsers);
        applicationContext.close();
    }
}
```

通过注解的定义我们可以看到@Qualifier 注解还可以作用到注解上面，也就是说可以对这个注解进行一些自定义的扩展：

```java
@Target({ElementType.FIELD, ElementType.METHOD, ElementType.PARAMETER, ElementType.TYPE, ElementType.ANNOTATION_TYPE})
@Retention(RetentionPolicy.RUNTIME)
@Inherited
@Documented
public @interface Qualifier {

	String value() default "";

}
```

接下来我们自定义一个注解：

```java
@Target({ElementType.FIELD, ElementType.METHOD, ElementType.PARAMETER, ElementType.TYPE, ElementType.ANNOTATION_TYPE})
@Retention(RetentionPolicy.RUNTIME)
@Inherited
@Documented
@Qualifier
public @interface UserGroup {

}
```

使用自定义注解来进行分组：

```java
/**
 * {@link org.springframework.beans.factory.annotation.Qualifier} 使用示例
 */
public class QualifierAnnotationDependencyInjectionDemo {

    @Autowired // SuperUser -> primary = true
    private User user;

    @Autowired
    @Qualifier("user") // 指定Bean名称或者ID
    private User namedUser;

    @Autowired
    private Collection<User> allUsers;

    @Autowired
    @Qualifier
    private Collection<User> qualifierUsers;

    @Autowired
    @UserGroup
    private Collection<User> groupedUsers;

    @Bean
    @Qualifier // 进行逻辑分组
    public User user1() {
        User user = new User();
        user.setId("7");
        return user;
    }

    @Bean
    @Qualifier
    public User user2() {
        User user = new User();
        user.setId("8");
        return user;
    }

    @Bean
    @UserGroup
    public User user3() {
        User user = new User();
        user.setId("9");
        return user;
    }

    @Bean
    @UserGroup
    public User user4() {
        User user = new User();
        user.setId("10");
        return user;
    }

    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(QualifierAnnotationDependencyInjectionDemo.class);
        applicationContext.refresh();
        XmlBeanDefinitionReader beanDefinitionReader = new XmlBeanDefinitionReader(applicationContext);
        String xmlResourcePath = "classpath:/META-INF/dependency-lookup-context.xml";
        beanDefinitionReader.loadBeanDefinitions(xmlResourcePath);
        QualifierAnnotationDependencyInjectionDemo demo = applicationContext.getBean(QualifierAnnotationDependencyInjectionDemo.class);
        // 输出SuperUSer Bean
        System.out.println("demo.user = " + demo.user);
        // 输出 user Bean
        System.out.println("demo.namedUser = " + demo.namedUser);
        // 输出 SuperUSer、user,注意这里输出的不是所有的user对象
        System.out.println("demo.allUsers = " + demo.allUsers);
        // 输出 user1、user2、user3和user4,这个时候这个集合元素也增加了,这种方式了类似继承
        System.out.println("demo.qualifierUsers = " + demo.qualifierUsers);
        // 输出 user3和user4
        System.out.println("demo.groupedUsers = " + demo.groupedUsers);
        applicationContext.close();
    }
}
```

最后我们来查看以下@LoadBalanced 注解的实现：

```java
@Target({ ElementType.FIELD, ElementType.PARAMETER, ElementType.METHOD })
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Inherited
@Qualifier
public @interface LoadBalanced {
}
```

## 延迟依赖注入

1. 使用 API ObjectFactory 延迟注入
   - 单一类型
   - 集合类型
2. 使用 API ObjectProvider 延迟注入（推荐，这里主要是基于安全性的考量）
   - 单一类型
   - 集合类型

使用 ObjectProvider 延迟注入的例子：

```java
/**
 * {@link org.springframework.beans.factory.ObjectProvider} 实现延迟依赖注入
 */
public class LazyAnnotationDependencyInjectionDemo {

    @Autowired
    private User user;  // 实时注入

    @Autowired
    private ObjectProvider<User> userObjectProvider; //延迟注入

    @Autowired
    private ObjectProvider<Set<User>> usersObjectFactory;

    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(LazyAnnotationDependencyInjectionDemo.class);
        applicationContext.refresh();
        XmlBeanDefinitionReader beanDefinitionReader = new XmlBeanDefinitionReader(applicationContext);
        String xmlResourcePath = "classpath:/META-INF/dependency-lookup-context.xml";
        beanDefinitionReader.loadBeanDefinitions(xmlResourcePath);
        LazyAnnotationDependencyInjectionDemo demo = applicationContext.getBean(LazyAnnotationDependencyInjectionDemo.class);
        System.out.println("demo.user = " + demo.user);
        System.out.println("demo.userObjectProvider = " + demo.userObjectProvider);
        System.out.println("demo.usersObjectFactory" + demo.usersObjectFactory);
        demo.userObjectProvider.forEach(System.out::println);
        applicationContext.close();
    }
}
```

## 依赖处理的过程

基础知识：

1. 入口-DefaultListableBeanFactory#resolveDependency
2. 依赖描述符-DependencyDescriptor
3. 自定义绑定候选对象处理器-AutowireCandidateResolver

首先观察以下依赖的描述类：

```java
public class DependencyDescriptor extends InjectionPoint implements Serializable {
	// 被注入的容器类
	private final Class<?> declaringClass;
	// 方法名称
	@Nullable
	private String methodName;
	// 构造器参数
	@Nullable
	private Class<?>[] parameterTypes;
	// 参数索引
	private int parameterIndex;
	// 属性名称
	@Nullable
	private String fieldName;
	// 是不是必须的
	private final boolean required;
	// 是不是饥饿的，@Lazy注解
	private final boolean eager;
	// 嵌入层次
	private int nestingLevel = 1;
	// 包含类
	@Nullable
	private Class<?> containingClass;
	// 泛型处理
	@Nullable
	private transient volatile ResolvableType resolvableType;
	// 类型描述
	@Nullable
	private transient volatile TypeDescriptor typeDescriptor;
}
```

首先改造以下我们之前看到的例子：

```java
/**
 * 注解驱动的依赖注入过程
 */
public class AnnotationDependencyInjectionResolutionDemo {

    @Autowired
    private User user;  // DependencyDescriptor ->
                        // 必须（required=true）
                        // 实时注入（eager=true）
                        // 通过类型查找（User.class）
                        // 字段名称（“user”）
                        // 是否首要（primary=true）

    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(AnnotationDependencyInjectionResolutionDemo.class);
        applicationContext.refresh();
        XmlBeanDefinitionReader beanDefinitionReader = new XmlBeanDefinitionReader(applicationContext);
        String xmlResourcePath = "classpath:/META-INF/dependency-lookup-context.xml";
        beanDefinitionReader.loadBeanDefinitions(xmlResourcePath);
        AnnotationDependencyInjectionResolutionDemo demo = applicationContext.getBean(AnnotationDependencyInjectionResolutionDemo.class);
        System.out.println("demo.user = " + demo.user);
        applicationContext.close();
    }
}
```

我们在 DefaultListableBeanFactory#resolveDependency 处打个断点进行观察：

![image-20210624205345978](https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210624205345978.png)

方法会继续往下执行到 doResolveDependency 方法：

![image-20210624205434583](https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210624205434583.png)

集合注入和单个类型的注入略微有点差别，首先我们增加一个成员变量：

```java
 	@Autowired          // 集合类型的依赖注入
    private Map<String,User> users;  // user SuperUser
```

这个时候在返回的时候就会进行判断，判断返回的类型是什么，然后然后把结果放进去进行返回：

```java
	@Nullable
	private Object resolveMultipleBeans(DependencyDescriptor descriptor, @Nullable String beanName,
			@Nullable Set<String> autowiredBeanNames, @Nullable TypeConverter typeConverter) {

		Class<?> type = descriptor.getDependencyType();

		if (descriptor instanceof StreamDependencyDescriptor) {
			Map<String, Object> matchingBeans = findAutowireCandidates(beanName, type, descriptor);
			if (autowiredBeanNames != null) {
				autowiredBeanNames.addAll(matchingBeans.keySet());
			}
			Stream<Object> stream = matchingBeans.keySet().stream()
					.map(name -> descriptor.resolveCandidate(name, type, this))
					.filter(bean -> !(bean instanceof NullBean));
			if (((StreamDependencyDescriptor) descriptor).isOrdered()) {
				stream = stream.sorted(adaptOrderComparator(matchingBeans));
			}
			return stream;
		}
		else if (type.isArray()) {
			Class<?> componentType = type.getComponentType();
			ResolvableType resolvableType = descriptor.getResolvableType();
			Class<?> resolvedArrayType = resolvableType.resolve(type);
			if (resolvedArrayType != type) {
				componentType = resolvableType.getComponentType().resolve();
			}
			if (componentType == null) {
				return null;
			}
			Map<String, Object> matchingBeans = findAutowireCandidates(beanName, componentType,
					new MultiElementDescriptor(descriptor));
			if (matchingBeans.isEmpty()) {
				return null;
			}
			if (autowiredBeanNames != null) {
				autowiredBeanNames.addAll(matchingBeans.keySet());
			}
			TypeConverter converter = (typeConverter != null ? typeConverter : getTypeConverter());
			Object result = converter.convertIfNecessary(matchingBeans.values(), resolvedArrayType);
			if (result instanceof Object[]) {
				Comparator<Object> comparator = adaptDependencyComparator(matchingBeans);
				if (comparator != null) {
					Arrays.sort((Object[]) result, comparator);
				}
			}
			return result;
		}
		else if (Collection.class.isAssignableFrom(type) && type.isInterface()) {
			Class<?> elementType = descriptor.getResolvableType().asCollection().resolveGeneric();
			if (elementType == null) {
				return null;
			}
			Map<String, Object> matchingBeans = findAutowireCandidates(beanName, elementType,
					new MultiElementDescriptor(descriptor));
			if (matchingBeans.isEmpty()) {
				return null;
			}
			if (autowiredBeanNames != null) {
				autowiredBeanNames.addAll(matchingBeans.keySet());
			}
			TypeConverter converter = (typeConverter != null ? typeConverter : getTypeConverter());
			Object result = converter.convertIfNecessary(matchingBeans.values(), type);
			if (result instanceof List) {
				if (((List<?>) result).size() > 1) {
					Comparator<Object> comparator = adaptDependencyComparator(matchingBeans);
					if (comparator != null) {
						((List<?>) result).sort(comparator);
					}
				}
			}
			return result;
		}
        // Map类型
		else if (Map.class == type) {
            // 获取到users字段的Map的泛型信息
			ResolvableType mapType = descriptor.getResolvableType().asMap();
			Class<?> keyType = mapType.resolveGeneric(0);
			if (String.class != keyType) {
				return null;
			}
			Class<?> valueType = mapType.resolveGeneric(1);
			if (valueType == null) {
				return null;
			}
			Map<String, Object> matchingBeans = findAutowireCandidates(beanName, valueType,
					new MultiElementDescriptor(descriptor));
			if (matchingBeans.isEmpty()) {
				return null;
			}
			if (autowiredBeanNames != null) {
				autowiredBeanNames.addAll(matchingBeans.keySet());
			}
			return matchingBeans;
		}
		else {
			return null;
		}
	}
```

当进行集合类型的注入时，定义 Bean 的顺序也就是加载 Bean 的顺序，也是初始化 Bean 的时候的顺序。

在 Java8 之后，也可以注入 Optional 类型的字段：

```java
	@Autowired
    private Optional<User> userOptional;
```

当注入的类型时延迟查找时，实际上会返回一个代理对象：

```java
	@Autowired
    @Lazy
    private User lazyUser;
```

总的来说，依赖注入的处理主要就是由以下两个方法来完成的：

```java
	@Override
	@Nullable
	public Object resolveDependency(DependencyDescriptor descriptor, @Nullable String requestingBeanName,
			@Nullable Set<String> autowiredBeanNames, @Nullable TypeConverter typeConverter) throws BeansException {

		descriptor.initParameterNameDiscovery(getParameterNameDiscoverer());
        // 对于Optional类型的判断
		if (Optional.class == descriptor.getDependencyType()) {
			return createOptionalDependency(descriptor, requestingBeanName);
		}
		else if (ObjectFactory.class == descriptor.getDependencyType() ||
				ObjectProvider.class == descriptor.getDependencyType()) {
			return new DependencyObjectProvider(descriptor, requestingBeanName);
		}
		else if (javaxInjectProviderClass == descriptor.getDependencyType()) {
			return new Jsr330Factory().createDependencyProvider(descriptor, requestingBeanName);
		}
		else {
			Object result = getAutowireCandidateResolver().getLazyResolutionProxyIfNecessary(
					descriptor, requestingBeanName);
			if (result == null) {
				result = doResolveDependency(descriptor, requestingBeanName, autowiredBeanNames, typeConverter);
			}
			return result;
		}
	}

	@Nullable
	public Object doResolveDependency(DependencyDescriptor descriptor, @Nullable String beanName,
			@Nullable Set<String> autowiredBeanNames, @Nullable TypeConverter typeConverter) throws BeansException {

		InjectionPoint previousInjectionPoint = ConstructorResolver.setCurrentInjectionPoint(descriptor);
		try {
			Object shortcut = descriptor.resolveShortcut(this);
			if (shortcut != null) {
				return shortcut;
			}

			Class<?> type = descriptor.getDependencyType();
			Object value = getAutowireCandidateResolver().getSuggestedValue(descriptor);
			if (value != null) {
				if (value instanceof String) {
					String strVal = resolveEmbeddedValue((String) value);
					BeanDefinition bd = (beanName != null && containsBean(beanName) ?
							getMergedBeanDefinition(beanName) : null);
					value = evaluateBeanDefinitionString(strVal, bd);
				}
				TypeConverter converter = (typeConverter != null ? typeConverter : getTypeConverter());
				try {
					return converter.convertIfNecessary(value, type, descriptor.getTypeDescriptor());
				}
				catch (UnsupportedOperationException ex) {
					// A custom TypeConverter which does not support TypeDescriptor resolution...
					return (descriptor.getField() != null ?
							converter.convertIfNecessary(value, type, descriptor.getField()) :
							converter.convertIfNecessary(value, type, descriptor.getMethodParameter()));
				}
			}

			Object multipleBeans = resolveMultipleBeans(descriptor, beanName, autowiredBeanNames, typeConverter);
			if (multipleBeans != null) {
				return multipleBeans;
			}

			Map<String, Object> matchingBeans = findAutowireCandidates(beanName, type, descriptor);
			if (matchingBeans.isEmpty()) {
				if (isRequired(descriptor)) {
					raiseNoMatchingBeanFound(type, descriptor.getResolvableType(), descriptor);
				}
				return null;
			}

			String autowiredBeanName;
			Object instanceCandidate;

			if (matchingBeans.size() > 1) {
				autowiredBeanName = determineAutowireCandidate(matchingBeans, descriptor);
				if (autowiredBeanName == null) {
					if (isRequired(descriptor) || !indicatesMultipleBeans(type)) {
						return descriptor.resolveNotUnique(descriptor.getResolvableType(), matchingBeans);
					}
					else {
						// In case of an optional Collection/Map, silently ignore a non-unique case:
						// possibly it was meant to be an empty collection of multiple regular beans
						// (before 4.3 in particular when we didn't even look for collection beans).
						return null;
					}
				}
				instanceCandidate = matchingBeans.get(autowiredBeanName);
			}
			else {
				// We have exactly one match.
				Map.Entry<String, Object> entry = matchingBeans.entrySet().iterator().next();
				autowiredBeanName = entry.getKey();
				instanceCandidate = entry.getValue();
			}

			if (autowiredBeanNames != null) {
				autowiredBeanNames.add(autowiredBeanName);
			}
			if (instanceCandidate instanceof Class) {
				instanceCandidate = descriptor.resolveCandidate(autowiredBeanName, type, this);
			}
			Object result = instanceCandidate;
			if (result instanceof NullBean) {
				if (isRequired(descriptor)) {
					raiseNoMatchingBeanFound(type, descriptor.getResolvableType(), descriptor);
				}
				result = null;
			}
			if (!ClassUtils.isAssignableValue(type, result)) {
				throw new BeanNotOfRequiredTypeException(autowiredBeanName, type, instanceCandidate.getClass());
			}
			return result;
		}
		finally {
			ConstructorResolver.setCurrentInjectionPoint(previousInjectionPoint);
		}
	}
```

## @Autowird 注入

@Autowired 注入总体过程：

1. 元信息解析
2. 依赖查找
3. 依赖注入（字段、方法）

核心处理方法：

```java
@Override
		protected void inject(Object bean, @Nullable String beanName, @Nullable PropertyValues pvs) throws Throwable {
             // 标注了@Autowired注解的字段
			Field field = (Field) this.member;
			Object value;
			if (this.cached) {
				try {
					value = resolvedCachedArgument(beanName, this.cachedFieldValue);
				}
				catch (NoSuchBeanDefinitionException ex) {
					// Unexpected removal of target bean for cached argument -> re-resolve
					value = resolveFieldValue(field, bean, beanName);
				}
			}
			else {
				value = resolveFieldValue(field, bean, beanName);
			}
			if (value != null) {
                 // 有可能时非public字段
				ReflectionUtils.makeAccessible(field);
                 // 最终通过反射的方式将依赖注入的对象设置到属性上
				field.set(bean, value);
			}
		}
```

在 XML 中配置信息解析的方法：

```java
	@Override
	public PropertyValues postProcessProperties(PropertyValues pvs, Object bean, String beanName) {
		InjectionMetadata metadata = findAutowiringMetadata(beanName, bean.getClass(), pvs);
		try {
			metadata.inject(bean, beanName, pvs);
		}
		catch (BeanCreationException ex) {
			throw ex;
		}
		catch (Throwable ex) {
			throw new BeanCreationException(beanName, "Injection of autowired dependencies failed", ex);
		}
		return pvs;
	}
```

这个方法会在 set 方法执行之前就执行，并且这个时候还没有进行类型转换。当这个类有父类的时候，会进行属性合并的操作，并且是在 postProcessProperties 之前执行的。

```java
@Override
	public void postProcessMergedBeanDefinition(RootBeanDefinition beanDefinition, Class<?> beanType, String beanName) {
		InjectionMetadata metadata = findAutowiringMetadata(beanName, beanType, null);
		metadata.checkConfigMembers(beanDefinition);
	}
```

一直会找到所有父类中的属性的方法：

```java
	@Nullable
	private MergedAnnotation<?> findAutowiredAnnotation(AccessibleObject ao) {
		MergedAnnotations annotations = MergedAnnotations.from(ao);
		for (Class<? extends Annotation> type : this.autowiredAnnotationTypes) {
			MergedAnnotation<?> annotation = annotations.get(type);
			if (annotation.isPresent()) {
				return annotation;
			}
		}
		return null;
	}
```

调用上述方法的地方：

```java
	ReflectionUtils.doWithLocalFields(targetClass, field -> {
				MergedAnnotation<?> ann = findAutowiredAnnotation(field);
				if (ann != null) {
                      // 可以看到就是在这里排除掉了static的字段
					if (Modifier.isStatic(field.getModifiers())) {
						if (logger.isInfoEnabled()) {
							logger.info("Autowired annotation is not supported on static fields: " + field);
						}
						return;
					}
					boolean required = determineRequiredStatus(ann);
					currElements.add(new AutowiredFieldElement(field, required));
				}
			});
```

可以看到在 postProcessMergedBeanDefinition 就完成了 Bean 的元信息的组装，并且在 postProcessProperties 执行的时候会包含调用 DefaultListableBeanFactory#resolveDependency 方法的过程。

## @Inject 和@Autowired 联系

@Inject 注入过程

- 如果 JSR-330 存在于 ClassPath 中，就直接复用 AutowiredAnnotationBeanPostProcessor 的实现。

在源代码中可以看到相关的逻辑：

这里首先要关注一个属性：

```java
private final Set<Class<? extends Annotation>> autowiredAnnotationTypes = new LinkedHashSet<>(4);
```

可以看到 autowiredAnnotationTypes 实际上是一个有序的 Set 集合，接下来是具体处理的逻辑：

```java
	public AutowiredAnnotationBeanPostProcessor() {
        // 依次插入Autowired、Value、inject
		this.autowiredAnnotationTypes.add(Autowired.class);
		this.autowiredAnnotationTypes.add(Value.class);
		try {
			this.autowiredAnnotationTypes.add((Class<? extends Annotation>)
					ClassUtils.forName("javax.inject.Inject", AutowiredAnnotationBeanPostProcessor.class.getClassLoader()));
			logger.trace("JSR-330 'javax.inject.Inject' annotation found and supported for autowiring");
		}
		catch (ClassNotFoundException ex) {
			// JSR-330 API not available - simply skip.
		}
	}

```

可以看到实际上还可以进行复合注解，并且在处理的时候：

```java
	@Nullable
	private MergedAnnotation<?> findAutowiredAnnotation(AccessibleObject ao) {
		MergedAnnotations annotations = MergedAnnotations.from(ao);
		for (Class<? extends Annotation> type : this.autowiredAnnotationTypes) {
			MergedAnnotation<?> annotation = annotations.get(type);
			if (annotation.isPresent()) {
				return annotation;
			}
		}
		return null;
	}
```

因此，如果要使用@Inject 注解，就需要引入依赖：

```xml
<dependency>
    <groupId>javax.inject</groupId>
    <artifactId>javax.inject</artifactId>
    <version>1</version>
</dependency>
```

可以发现@Inject 和@Autowired 注解在处理的上完全一样的，都是使用 AutowiredAnnotationBeanPostProcessor 来处理依赖注入的过程。

## Java 通用注解原理

CommonAnnotationBeanPostProcessor

1. 注入注解
   - javax.xml.ws.WebServiceRef
   - javax.ejb.EJB
   - javax.annotation.Resource
2. 生命周期注解
   - javax.annotation.PostConstruct
   - javax.annotation.PreDestory

CommonAnnotationBeanPostProcessor 和 AutowiredAnnotationBeanPostProcessor 大概的实现逻辑是如出一辙的，只是在细微的地方略有差别。

CommonAnnotationBeanPostProcessor 实现了 InitDestroyAnnotationBeanPostProcessor 接口

```java
public class CommonAnnotationBeanPostProcessor extends InitDestroyAnnotationBeanPostProcessor
		implements InstantiationAwareBeanPostProcessor, BeanFactoryAware, Serializable {
		// ...
		}
```

在 InitDestroyAnnotationBeanPostProcessor 中也可以看到 postProcessMergedBeanDefinition 这个方法：

![image-20210624205533354](https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210624205533354.png)

这里只是元信息不太一样，这主要是 LifecycleMetadata 中包含了初始化和销毁两个阶段。

同样 CommonAnnotationBeanPostProcessor 也有 postProcessProperties 的方法：

![image-20210624205605481](https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210624205605481.png)

对于生命周期的注解的处理，可以从构造方法中看出：

```java
public CommonAnnotationBeanPostProcessor() {
    	// 优先级是倒数第四位的
		setOrder(Ordered.LOWEST_PRECEDENCE - 3);
		setInitAnnotationType(PostConstruct.class);
		setDestroyAnnotationType(PreDestroy.class);
		ignoreResourceType("javax.xml.ws.WebServiceContext");
	}
```

CommonAnnotationBeanPostProcessor 会在 AutowiredAnnotationBeanPostProcessor 之前进行处理，这一点，可以通过实现的 PriorityOrdered 接口，看到属性中定义的顺序来进行确认。

## 自定义依赖注入注解

1. 基于 AutowiredAnnotationBeanPostProcessor 实现
2. 自定义实现
   - 生命周期处理
     - InstantiationAwareBeanPostProcessor
     - MergedBeanDefinitionPostProcessor
   - 元数据
     - InjectedElement
     - InjectionMetadata

基于 AutowiredAnnotationBeanPostProcessor 实现自定义依赖注入相对比较容易，如果使用自定义实现，就比较麻烦。

```java
/**
 * 自定义注解
 */
@Target({ElementType.CONSTRUCTOR, ElementType.METHOD, ElementType.FIELD})
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Autowired
public @interface MyAutowired {
    boolean required() default true;
}

```

这里我们不对@Autowired 做任何的扩展，仅仅使用它进行元标注，定义完成之后使用 MyAutowired 进行注入：

```java
 	@MyAutowired
    private Optional<User> userOptional;
```

发现依然可以正常地工作，接下来我们自定义一个注解：

```java
/**
 * 自定义依赖注入注解
 */
@Target({ElementType.CONSTRUCTOR, ElementType.METHOD, ElementType.FIELD})
@Retention(RetentionPolicy.RUNTIME)
@Documented
public @interface InjectedUser {
}
```

将我们自定义的注解类型添加到 AutowiredAnnotationBeanPostProcessor 中：

```java
    @Bean(name = AUTOWIRED_ANNOTATION_PROCESSOR_BEAN_NAME) //注意这里是static方法，会提前初始化方法
    public static AutowiredAnnotationBeanPostProcessor beanPostProcessor() {
        AutowiredAnnotationBeanPostProcessor beanPostProcessor = new AutowiredAnnotationBeanPostProcessor();
        // 替换原有注解处理，使用新注解@InjectedUser，原来的注解会失效
//        beanPostProcessor.setAutowiredAnnotationType(InjectedUser.class);
        // 保留原来的方式，添加新的注解，@Autowired + @InjectedUser
        Set<Class<? extends Annotation>> autowiredAnnotationTypes = new LinkedHashSet<>(Arrays.asList(Autowired.class, Inject.class, InjectedUser.class));
        beanPostProcessor.setAutowiredAnnotationTypes(autowiredAnnotationTypes);
        return beanPostProcessor;
    }
```

测试我们的注解是否生效：

```java
 	@InjectedUser
    private User myInjectedUser;
```

答案是肯定的。如何实现新老注解的兼容的注入方法呢？

首先注入一个 AutowiredAnnotationBeanPostProcessor，并设置我们自定义的注解

```java
	@Bean
    @Order(Ordered.LOWEST_PRECEDENCE - 3)
    public static AutowiredAnnotationBeanPostProcessor beanPostProcessor() {
        AutowiredAnnotationBeanPostProcessor beanPostProcessor = new AutowiredAnnotationBeanPostProcessor();
        beanPostProcessor.setAutowiredAnnotationType(InjectedUser.class);
        return beanPostProcessor;
    }
```

​ 在 AnnotationConfigUtils#registerAnnotationConfigProcessors 中

```java
if (!registry.containsBeanDefinition(AUTOWIRED_ANNOTATION_PROCESSOR_BEAN_NAME)) {
			RootBeanDefinition def = new RootBeanDefinition(AutowiredAnnotationBeanPostProcessor.class);
			def.setSource(source);
			beanDefs.add(registerPostProcessor(registry, def, AUTOWIRED_ANNOTATION_PROCESSOR_BEAN_NAME));
		}
```

可以看到如果 AutowiredAnnotationBeanPostProcessor 这个 Bean 存在的话，就不注册，不存在的会注册一个默认的，因为我们这里注入 AutowiredAnnotationBeanPostProcessor 采用的 static，就会首先使用我们注册的 AutowiredAnnotationBeanPostProcessor 来进行依赖注入，这时候，在应用上下文中有两个 AutowiredAnnotationBeanPostProcessor 来进行处理。

## 面试题

### 有多少种依赖注入的方式

构造器注入、Setter 注入、字段注入、方法注入、接口回调注入

### 你偏好构造器注入还是 Setter 注入?

两种依赖注入的方式均可以使用，如果是必须依赖的话，那么推荐使用构造器注入，Setter 注入用于可选依赖。

### Spring 依赖注入的来源有哪些？

待续...

# Spring IoC 依赖来源

## 依赖查找的来源

查找来源：

| 来源                  | 配置元数据                            |
| --------------------- | ------------------------------------- |
| Spring BeanDefinition | `<bean id="user" class="org...User">` |
|                       | @Bean<br />public User user(){...}    |
|                       | BeanDefinitionBuilder                 |
| 单例对象              | API 实现                              |

## 依赖注入的来源

注入来源：

| 来源                               | 配置元数据                            |
| ---------------------------------- | ------------------------------------- |
| Spring BeanDefinition              | `<bean id="user" class="org...User">` |
|                                    | @Bean<br />public User user(){...}    |
|                                    | BeanDefinitionBuilder                 |
| 单例对象                           | API 实现                              |
| 非 Spring 容器管理对象（游离对象） |                                       |

AbstractApplicationContext#refresh()方法会调用 prepareBeanFactory(beanFactory)方法，这个方法中会注入一些 Bean：

```java
		// BeanFactory interface not registered as resolvable type in a plain factory.
		// MessageSource registered (and found for autowiring) as a bean.
		beanFactory.registerResolvableDependency(BeanFactory.class, beanFactory);
		// 注意接下来的都是当前ApplicationContext对象
		beanFactory.registerResolvableDependency(ResourceLoader.class, this);
		beanFactory.registerResolvableDependency(ApplicationEventPublisher.class, this);
		beanFactory.registerResolvableDependency(ApplicationContext.class, this);
```

实际上，注入了四个类型，两个对象。

```java
/**
 * 依赖来源示例
 */
public class DependencySourceDemo {

    // 注入在postProcessProperties方法执行，早于setter注入，也早于PostConstruct
    @Autowired
    private BeanFactory beanFactory;

    @Autowired
    private ResourceLoader resourceLoader;

    @Autowired
    private ApplicationContext applicationContext;

    @Autowired
    private ApplicationEventPublisher applicationEventPublisher;

    @PostConstruct
    public void init() {
        System.out.println("beanFactory == applicationContext: " + (beanFactory == applicationContext));
        System.out.println("beanFactory == applicationContext.getBeanFactory: " + (beanFactory == applicationContext.getAutowireCapableBeanFactory()));
        System.out.println("resourceLoader == applicationContext: " + (resourceLoader == applicationContext));
        System.out.println("applicationEventMulticaster == applicationContext: " + (applicationEventPublisher == applicationContext));
    }

    @PostConstruct
    public void initByLookup() {
        getBean(BeanFactory.class);
        getBean(ResourceLoader.class);
        getBean(ApplicationContext.class);
        getBean(ApplicationEventPublisher.class);
    }

    private <T> T getBean(Class<T> beanType) {
        try {
            return beanFactory.getBean(beanType);
        } catch (NoSuchBeanDefinitionException e) {
            System.err.println("当前类型" + beanType.getName() + "无法在BeanFactory中查找");
            return null;
        }
    }

    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(DependencySourceDemo.class);
        applicationContext.refresh();

        DependencySourceDemo demo = applicationContext.getBean(DependencySourceDemo.class);
        applicationContext.close();
    }
}
```

## Spring 容器管理和游离对象

依赖对象：

| 来源                  | Spring Bean 对象 | 生命周期管理 | 配置元信息 | 使用场景           |
| --------------------- | ---------------- | ------------ | ---------- | ------------------ |
| Spring BeanDefinition | 是               | 是           | 有         | 依赖查找、依赖注入 |
| 单体对象              | 是               | 否           | 无         | 依赖查找、依赖注入 |
| Resolvable Dependency | 否               | 否           | 无         | 依赖注入           |

## Spring BeanDefinition 作为依赖来源

要素：

1. 元数据：BeanDefinition
2. 注册：BeanDefinitionRegistry#registerBeanDefinition
3. 类型：延迟和非延迟
4. 顺序：Bean 生命周期顺序按照注册顺序

BeanDefinitionRegistry 有且仅有一个实现，就是 DefaultListableBeanFactory，首先有这样两个属性：

```java
// Map of bean definition objects, keyed by bean name
private final Map<String, BeanDefinition> beanDefinitionMap = new ConcurrentHashMap<>(256);
// List of bean definition names, in registration order.
private volatile List<String> beanDefinitionNames = new ArrayList<>(256);
```

在 registerBeanDefinition 方法中会这样保存数据：

```java
this.beanDefinitionMap.put(beanName, beanDefinition);
this.beanDefinitionNames.add(beanName);
```

可以看到这里除了保存 beanName 和 beanDefinition，还单独保存了 beanName，这样做的原因就是 ConcurrentHashMap 是无序的，而 ArrayList 是有序的，后面在初始化的时候，会根据这个 List 里面的 Bean 的名称，按照次序依次进行初始化操作。

## 单体对象作为依赖来源

要素：

1. 来源：外部普通 Java 对象（不一定是 POJO）
2. 注册：SingletonBeanRegistry#registerSinleton

限制：

1. 无生命周期管理
2. 无法实现延迟初始化 Bean

## Resolvable Dependency 作为依赖来源

要素：

- 注册：ConfigurableListableBeanFactory#registerResolvableDependency

限制：

1. 无生命周期管理
2. 无法延迟初始化 Bean
3. 无法通过依赖查找

```java
/**
 * ResolvableDependency作为依赖来源
 */
public class ResolvableDependencySourceDemo {

    @Autowired
    private String value;

    @PostConstruct
    public void init() {
        System.out.println(value);
    }
    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(ResolvableDependencySourceDemo.class);
        // 只能用于类型方面的依赖注入
        applicationContext.addBeanFactoryPostProcessor(beanFactory -> {
            beanFactory.registerResolvableDependency(String.class,"hello,world");
        });
        applicationContext.refresh();
        applicationContext.close();
    }
}
```

## 外部化配置作为依赖来源

要素：

- 类型：非常规 Spring 对象依赖来源

限制：

1. 无生命周期管理
2. 无法实现延迟初始化 Bean
3. 无法通过依赖查找

外部化配置的示例：

```java
/**
 * 外部化配置作为依赖来源示例
 */
@PropertySource(value = "META-INF/default.properties",encoding = "GBK")
@Configuration
public class ExternalConfigurationDependencySourceDemo {

    @Value("${user.id}")
    private String id;

    @Value("${user.resource}")
    private Resource resource;

    // 如果是中文，这里会显示操作系统登录的用户名，而不是在配置文件中配置的信息。这是因为user.name是一个系统属性。
//    @Value("${user.name}")
//    private String name;
    // 直接输出会显示乱码,需要设置编码
    @Value("${usr.name}")
    private String name;

    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(ExternalConfigurationDependencySourceDemo.class);
        applicationContext.refresh();
        ExternalConfigurationDependencySourceDemo demo = applicationContext.getBean(ExternalConfigurationDependencySourceDemo.class);
        System.out.println("id: " + demo.id);
        System.out.println("resource: " + demo.resource);
        System.out.println("name: " + demo.name);

        applicationContext.close();
    }
}
```

实现原理就是 DefaultListableBeanFactory#doResolveDependency 中：

![image-20210624205723539](https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210624205723539.png)

会通过接下来的方法进行替换，将属性替换为配置文件中的值：

```java
String strVal = resolveEmbeddedValue((String) value);
```

## 面试题

### 依赖注入和依赖查找的依赖来源是否相同？

否，依赖查找的来源仅限于 Spring BeanDefinition 以及单例对象，而依赖注入的来源还包括了 Resolvable Dependency 以及@Value 所标注的外部化配置。

### 单例对象能在 IoC 容器启动后注册吗？

可以的，单例对象注册与 BeanDefinition 不同，BeanDefinition 会被 ConfigurableListableBeanFactory#freezeConfiguration()方法影响，从而冻结注册，单例对象则没有这个限制。

### Spring 依赖注入的来源有哪些？

Spring BeanDefinition、单例对象、Resolvable Dependency、@Value 外部化配置

# Spring Bean 作用域

## 作用域简介

| 来源        | 说明                                                       |
| ----------- | ---------------------------------------------------------- |
| singleton   | 默认 Spring Bean 作用域，一个 BeanFactory 有且仅有一个实例 |
| prototype   | 原型作用域，每次依赖查找和依赖注入生成新 Bean 对象         |
| request     | 将 Spring Bean 存储在 ServletRequest 上下文中              |
| session     | 将 Spring Bean 存储在 HttpSession 中                       |
| application | 将 Spring Bean 存储在 ServletContext 中                    |

笼统而言，我们只要记住单例和原型两种即可，其余三种主要是为了服务端模板引擎渲染，包括 JSP、Velocity、FreeMarker。

## singleton 作用域

单例模式是在一定范围内是全局共享的，但是这个范围是有限的。通过观察 BeanDefinition 源代码可以发现，其实只有 singleton 和 prototype 这两个作用域相关的方法：

```java
	// 是否是单例
	boolean isSingleton();
	// 是否是原型
	boolean isPrototype();
```

单例模式的示例图：

![image-20210624205747975](https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210624205747975.png)

这里有一个误区就是，singleton 和 prototype 并没有互斥的关系，是可以同时存在的，当然，如果同时存在的话，可能行为会有一些问题。

## prototype 作用域

多例模式的示意图：

![image-20210624205818521](https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210624205818521.png)

多例和单例比较的示例：

```java
/**
 * Bean的作用域示例
 */
public class BeanScopeDemo {

    @Bean
    // 默认的scop就是“singleton”
    public static User singletonUser() {
        return createUser();
    }

    @Bean
    @Scope(ConfigurableBeanFactory.SCOPE_PROTOTYPE)
    public static User prototypeUser() {
        return createUser();
    }

    private static User createUser() {
        User user = new User();
        user.setId(String.valueOf(System.nanoTime()));
        return user;
    }

    @Autowired
    @Qualifier("singletonUser")
    private User singletonUser;

    @Autowired
    @Qualifier("singletonUser")
    private User singletonUser1;

    @Autowired
    @Qualifier("prototypeUser")
    private User prototypeUser;

    @Autowired
    @Qualifier("prototypeUser")
    private User prototypeUser1;

    @Autowired
    @Qualifier("prototypeUser")
    private User prototypeUser2;

    @Autowired
    private Map<String,User> users;


    private static void scopedBeansByInjection(AnnotationConfigApplicationContext applicationContext) {
        BeanScopeDemo beanScopeDemo = applicationContext.getBean(BeanScopeDemo.class);
        System.out.println("beanScopeDemo.singletonUser = " + beanScopeDemo.singletonUser);
        System.out.println("beanScopeDemo.singletonUser1 = " + beanScopeDemo.singletonUser1);
        System.out.println("beanScopeDemo.prototypeUser1 = " + beanScopeDemo.prototypeUser);
        System.out.println("beanScopeDemo.prototypeUser2 = " + beanScopeDemo.prototypeUser1);
        System.out.println("beanScopeDemo.prototypeUser3 = " + beanScopeDemo.prototypeUser2);
        System.out.println("beanScopeDemo.users = " + beanScopeDemo.users);
    }

    private static void scopedBeansByLookup(AnnotationConfigApplicationContext applicationContext) {
        for (int i = 0; i < 3; i++) {
            User singletonUser = applicationContext.getBean("singletonUser", User.class);
            // singletonUser是共享的Bean对象
            System.out.println("singletonUser = " + singletonUser.getId());
            // prototypeUser是每次依赖查找都会生成新的Bean对象
            User prototypeUser = applicationContext.getBean("prototypeUser", User.class);
            System.out.println("prototypeUser = " + prototypeUser.getId());

        }
    }

    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(BeanScopeDemo.class);
        applicationContext.refresh();
        // 结论一：
        // singleton Bean无论依赖查找还是依赖注入均为同一个对象
        // prototype Bean无论依赖查找还是依赖注入均为新生成的对象
        // 结论二：
        // 如果依赖注入集合类型的对象，singleton Bean和prototype Bean均会存在一个
        // prototype Bean有别于其他地方的依赖注入
        scopedBeansByLookup(applicationContext);
        scopedBeansByInjection(applicationContext);
        applicationContext.close();
    }
}
```

注意事项：

Spring 容器没有办法管理 prototype Bean 的完整生命周期，也没有办法记录实例的存在。销毁回调方法将不会执行，可以利用 BeanPostProcess 进行清扫工作。

```java
public class User implements BeanNameAware {
    private String id;

    private String name;

    private transient String beanName;

    public String getId() {
        return id;
    }

    public void setId(String id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "User{" +
                "id='" + id + '\'' +
                ", name='" + name + '\'' +
                '}';
    }
    public static User createUser() {
        User user = new User();
        user.setName("createUser");
        user.setId("123");
        return user;
    }

    @PostConstruct
    public void init() {
        System.out.println("User Bean [" + beanName + "]初始化...");
    }

    @PreDestroy
    public void destory() {
        System.out.println("User Bean [" + beanName + "]销毁化...");
    }

    @Override
    public void setBeanName(String name) {
        this.beanName = name;
    }
}
```

运行刚才的例子不难看出，初始化的方法每次还是会被调用，但是销毁方法只有单例的 Bean 才会调用，那么如何销毁 prototype 的 Bean 呢？一种做法就是前面提到的 BeanPostProcess：

```java
        applicationContext.addBeanFactoryPostProcessor(beanFactory -> {
            beanFactory.addBeanPostProcessor(new BeanPostProcessor() {
                @Override
                public Object postProcessAfterInitialization(Object bean, String beanName) throws BeansException {
                    System.out.printf("%s Bean名称: %s 在初始化后回调...%n", bean.getClass().getName(), beanName);
                    return bean;
                }
            });
        });
```

在这个方法里面可以执行一些销毁的逻辑，但是使用这种方式，可能会有一些意想不到的结果，因为创建好的 prototype 的 Bean 通常而言都是马上要使用的，而不需要在它上面增加一些额外的操作，更为推荐的方式，是在维护 prototype 的 Bean 的类中，利用它的生命周期方法，对于所管理的 prototype 类型的类进行销毁：

```java
public class BeanScopeDemo implements DisposableBean {

    @Bean
    // 默认的scop就是“singleton”
    public static User singletonUser() {
        return createUser();
    }

    @Bean
    @Scope(ConfigurableBeanFactory.SCOPE_PROTOTYPE)
    public static User prototypeUser() {
        return createUser();
    }

    private static User createUser() {
        User user = new User();
        user.setId(String.valueOf(System.nanoTime()));
        return user;
    }

    @Autowired
    @Qualifier("singletonUser")
    private User singletonUser;

    @Autowired
    @Qualifier("singletonUser")
    private User singletonUser1;

    @Autowired
    @Qualifier("prototypeUser")
    private User prototypeUser;

    @Autowired
    @Qualifier("prototypeUser")
    private User prototypeUser1;

    @Autowired
    @Qualifier("prototypeUser")
    private User prototypeUser2;

    @Autowired
    private Map<String, User> users;

    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(BeanScopeDemo.class);
        applicationContext.refresh();
        applicationContext.close();
    }

    @Override
    public void destroy() {
        System.out.println("当前BeanScopeDemo Bean 正在销毁中");
        this.prototypeUser.destory();
        this.prototypeUser1.destory();
        this.prototypeUser2.destory();
        for (Map.Entry<String, User> entry : this.users.entrySet()) {
            String beanName = entry.getKey();
            BeanDefinition beanDefinition = beanFactory.getBeanDefinition(beanName);
            if (beanDefinition.isPrototype()) {
                User user = entry.getValue();
                user.destory();
            }
        }
        System.out.println("当前BeanScopeDemo Bean 销毁已完成...");
    }
}

```

## request 作用域

1. 配置
   - XML - `<bean class="..." scope="request">`
   - Java 注解 - @RequestScope 或@Scope（WebApplicationContext.SCOPE_REQUEST）
2. 实现
   - API - RequestScope

## session 作用域

1. 配置
   - XML - `<bean class="..." scope="session">`
   - Java 注解 - @SessionScope 或@Scope（WebApplicationContext.SCOPE_SESSION）
2. 实现
   - API - SessionScope

request 作用域的对象，每次请求都会返回一个新的对象，并且对象会经历初始化和销毁两个过程，而 session 作用域，在同一个 cookie 的情况下，每次返回的都是同一个对象，这个时候对象只会经历初始化的过程，而不会对 Bean 进行销毁。无论是 request 还是 session，返回的对象都是经过 cglib 代理的对象。

## application 作用域

1. 配置
   - XML - `<bean class="..." scope="application">`
   - Java 注解 - @ApplicationScope 或@Scope（WebApplicationContext.APPLICATION）
2. 实现
   - API - ApplicationScope

application 作用域的 Bean 可以在 ServletContext 中直接获取到。一个 JavaWeb 应用只创建一个 ServletContext 对象，应用在启动的时候创建 ServletContext 对象，在服务器关闭的时候销毁，使用 ServletContext 获取到的 Bean 对象也是经过 cglib 代理的对象，Bean 的名称为`scopedTarget.beanName`

## 自定义 Bean 作用域

1. 实现 Scope

   - org.springframework.beans.factory.config.Scope

2. 注册 Scope

   - API - org.springframework.beans.factory.config.ConfigurableBeanFactory#registerScope

   - 配置：

     ```xml
     <bean class="org.springframework.beans.factory.config.CustomScopeConfigurer">
          <property name="scopes">
               <map>
                    <entry key="...">
                    </entry>
               </map>
          </property>
     </bean>
     ```

自定义作用的相关示例，首先进行定义：

```java
public class ThreadLocalScope implements Scope {

    public static final String SCOP_NAME = "thread-local";

    private final NamedThreadLocal<Map<String, Object>> threadLocal = new NamedThreadLocal("thread-local-scope") {
        @Override
        public Map<String, Object> initialValue() {
            return new HashMap<>();
        }
    };

    @Override
    public Object get(String name, ObjectFactory<?> objectFactory) {
        // 非空
        Map<String, Object> context = getContext();
        Object object = context.get(name);
        if (object == null) {
            object = objectFactory.getObject();
            context.put(name, object);
        }
        return object;
    }

    private Map<String, Object> getContext() {
        return threadLocal.get();
    }

    @Override
    public Object remove(String name) {
        Map<String, Object> context = getContext();
        return context.remove(name);
    }

    @Override
    public void registerDestructionCallback(String name, Runnable callback) {
        // TODO
    }

    @Override
    public Object resolveContextualObject(String key) {
        Map<String, Object> context = getContext();
        return context.get(key);
    }

    @Override
    public String getConversationId() {
        Thread thread = Thread.currentThread();
        return String.valueOf(thread.getId());
    }
}
```

接下来进行注册并且测试是否成功：

```java
public class ThreadLocalScopeDemo {
    @Bean
    @Scope(ThreadLocalScope.SCOP_NAME)
    public User user() {
        return createUser();
    }

    private static User createUser() {
        User user = new User();
        user.setId(String.valueOf(System.nanoTime()));
        return user;
    }

    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(ThreadLocalScopeDemo.class);
        applicationContext.addBeanFactoryPostProcessor(beanFactory -> {
                    beanFactory.registerScope(ThreadLocalScope.SCOP_NAME, new ThreadLocalScope());
                }
        );
        applicationContext.refresh();
        scopedBeansByLookup(applicationContext);
        applicationContext.close();
    }

    private static void scopedBeansByLookup(AnnotationConfigApplicationContext applicationContext) {
        // 单个线程下，返回的永远是同一个Bean
//        for (int i = 0; i < 3; i++) {
//            User user = applicationContext.getBean("user", User.class);
//            System.out.println("user = " + user.getId());
//        }
        for (int i = 0; i < 3; i++) {
            Thread thread = new Thread(() -> {
                User user = applicationContext.getBean("user", User.class);
                System.out.printf("[Thread id: %d] user = %s%n", Thread.currentThread().getId(), user);
            });
            thread.start();
            // 强制线程执行完成
            try {
                thread.join();
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}
```

## 面试题

### Spring 内建的 Bean 的作用域有几种？

sington、prototype、request、session、application 以及 websocket

### singleton Bean 是否在一个应用中是唯一的？

否，singleton bean 仅在当前 Spring IoC 容器（BeanFactory）中是单例对象。

### "application" Bean 是否被其他方案他替代？

可以的，实际上，"application" Bean 与"singleton" Bean 没有本质区别。

# Spring Bean 生命周期

## 元信息配置阶段

BeanDefinition 的配置方式：

1. 面向资源
   - XML 配置
   - Properties 资源配置
2. 面向注解
3. 面向 API

这里除了 Properties 资源配置我们没有见到过外，其他的都有相关的示例。

```properties
# 注意这里必须这么写，不能写user.class
user.(class) = org.jyc.thinking.in.spring.ioc.overview.dependency.domain.User
user.id = 001
user.name = 胡先森
user.city = HANGZHOU
```

相关的演示示例：

```java
public class BeanMetadataConfigurationDemo {
    public static void main(String[] args) {
        DefaultListableBeanFactory beanFactory = new DefaultListableBeanFactory();
        // 实例化PropertiesBeanDefinitionReader
        PropertiesBeanDefinitionReader propertiesBeanDefinitionReader = new PropertiesBeanDefinitionReader(beanFactory);
        String location = "classpath:/META-INF/user.properties";
        int beanNumbers = propertiesBeanDefinitionReader.loadBeanDefinitions(location);
        System.out.println("已加载的BeanDefinitiond的数量：" + beanNumbers);
        // 通过Bean ID和类型进行依赖查找
        User user = beanFactory.getBean("user", User.class);
        System.out.println(user.toString());
    }
}
```

## 元信息解析阶段

主要分为两种：

1. 面向资源 BeanDefinition 解析
   - BeanDefinitionReader
   - XML 解析器 - BeanDefinitionParser
2. 面向注解 BeanDefinition 解析
   - AnnotatedBeanDefinitionReader

面向资源的情况我们在之前也有过相关的讨论，这里只介绍面向注解的 BeanDefinition 解析：

```java
public class AnnotatedBeanDefinitionParsingDemo {
    public static void main(String[] args) {
        DefaultListableBeanFactory beanFactory = new DefaultListableBeanFactory();
        // 基于Java 注解的 AnnotatedBeanDefinitionReader的实现
        AnnotatedBeanDefinitionReader beanDefinitionReader = new AnnotatedBeanDefinitionReader(beanFactory);
        int beanDefinitionCountBefore = beanFactory.getBeanDefinitionCount();
        // 注册当前类（非Componenet Class）
        beanDefinitionReader.registerBean(AnnotatedBeanDefinitionParsingDemo.class);
        int beanDefinitionCountAfter = beanFactory.getBeanDefinitionCount();
        int beanDefinitionCount = beanDefinitionCountAfter - beanDefinitionCountBefore;
        System.out.println("已加载的BeanDefinitiond的数量：" + beanDefinitionCount);
        // 普通Class作为Component注册到Spring IoC容器后，通常Bean的名称为类名的首字母小写（annotatedBeanDefinitionParsingDemo）
        // Bean名称生成来自于BeanNameGenerator，注解实现AnnotationBeanNameGenerator
        AnnotatedBeanDefinitionParsingDemo demo = beanFactory.getBean("annotatedBeanDefinitionParsingDemo", AnnotatedBeanDefinitionParsingDemo.class);
        System.out.println(demo);
    }
}
```

默认生成 Bean 的名称的部分代码：

```java
	protected String buildDefaultBeanName(BeanDefinition definition) {
		String beanClassName = definition.getBeanClassName();
		Assert.state(beanClassName != null, "No bean class name set");
		String shortClassName = ClassUtils.getShortName(beanClassName);
		return Introspector.decapitalize(shortClassName);
	}

```

## 注册阶段

BeanDefinition 注册的核心接口：BeanDefinitionRegistry，它有且仅有一个实现类就是 DefaultListableBeanFactory。DefaultListableBeanFactory#registerBeanDefinition 的逻辑如下：

```java
public void registerBeanDefinition(String beanName, BeanDefinition beanDefinition)
			throws BeanDefinitionStoreException {

		Assert.hasText(beanName, "Bean name must not be empty");
		Assert.notNull(beanDefinition, "BeanDefinition must not be null");

		if (beanDefinition instanceof AbstractBeanDefinition) {
			try {
				((AbstractBeanDefinition) beanDefinition).validate();
			}
			catch (BeanDefinitionValidationException ex) {
				throw new BeanDefinitionStoreException(beanDefinition.getResourceDescription(), beanName,
						"Validation of bean definition failed", ex);
			}
		}

		BeanDefinition existingDefinition = this.beanDefinitionMap.get(beanName);
    	// 当已经存在BeanDefinition的时候
		if (existingDefinition != null) {
              // 允许Bean重复注册
			if (!isAllowBeanDefinitionOverriding()) {
				throw new BeanDefinitionOverrideException(beanName, beanDefinition, existingDefinition);
			}
			else if (existingDefinition.getRole() < beanDefinition.getRole()) {
				// e.g. was ROLE_APPLICATION, now overriding with ROLE_SUPPORT or ROLE_INFRASTRUCTURE
				if (logger.isInfoEnabled()) {
					logger.info("Overriding user-defined bean definition for bean '" + beanName +
							"' with a framework-generated bean definition: replacing [" +
							existingDefinition + "] with [" + beanDefinition + "]");
				}
			}
			else if (!beanDefinition.equals(existingDefinition)) {
				if (logger.isDebugEnabled()) {
					logger.debug("Overriding bean definition for bean '" + beanName +
							"' with a different definition: replacing [" + existingDefinition +
							"] with [" + beanDefinition + "]");
				}
			}
			else {
				if (logger.isTraceEnabled()) {
					logger.trace("Overriding bean definition for bean '" + beanName +
							"' with an equivalent definition: replacing [" + existingDefinition +
							"] with [" + beanDefinition + "]");
				}
			}
			this.beanDefinitionMap.put(beanName, beanDefinition);
		}
		else {
             // 注册一个新的BeanDefinition
			if (hasBeanCreationStarted()) {
				// Cannot modify startup-time collection elements anymore (for stable iteration)
				synchronized (this.beanDefinitionMap) {
                      // 这里的beanDefinitionMap的类型是Map<String, BeanDefinition>,key就是Bean的名称，value就是对应的BeanDefinition
					this.beanDefinitionMap.put(beanName, beanDefinition);
                      // 这里之所以还要维护一个beanDefinitionNames是为了记住注册时候的Bean的顺序。
					List<String> updatedDefinitions = new ArrayList<>(this.beanDefinitionNames.size() + 1);
					updatedDefinitions.addAll(this.beanDefinitionNames);
					updatedDefinitions.add(beanName);
					this.beanDefinitionNames = updatedDefinitions;
					removeManualSingletonName(beanName);
				}
			}
			else {
				// Still in startup registration phase
				this.beanDefinitionMap.put(beanName, beanDefinition);
				this.beanDefinitionNames.add(beanName);
				removeManualSingletonName(beanName);
			}
			this.frozenBeanDefinitionNames = null;
		}

		if (existingDefinition != null || containsSingleton(beanName)) {
			resetBeanDefinition(beanName);
		}
		else if (isConfigurationFrozen()) {
			clearByTypeCache();
		}
	}
```

## BeanDefinition 合并阶段

BeanDefinition 合并：

1. 父子 BeanDefinition 合并
   - 当前 BeanFactory 查找
   - 层次性 BeanFactory 查找

相关的示例：

```java
public class MergedBeanDefinitionDemo {
    public static void main(String[] args) {
        DefaultListableBeanFactory beanFactory = new DefaultListableBeanFactory();
        // 基于XML资源BeanDefinitionReader 实现
        XmlBeanDefinitionReader xmlBeanDefinitionReader = new XmlBeanDefinitionReader(beanFactory);
        String location = "META-INF/dependency-lookup-context.xml";
        Resource resource = new ClassPathResource(location);
        EncodedResource encodedResource = new EncodedResource(resource, "UTF-8");
        int beanNumbers = xmlBeanDefinitionReader.loadBeanDefinitions(encodedResource);
        System.out.println("已加载的BeanDefinitiond的数量：" + beanNumbers);

        // 不需要合并BeanDefinition
        User user = beanFactory.getBean("user", User.class);
        System.out.println(user.toString());
        // 需要合并BeanDefinition
        SuperUser superUser = beanFactory.getBean("SuperUser", SuperUser.class);
        System.out.println(superUser.toString());
    }
}
```

递归查找

```java
	@Override
	public BeanDefinition getMergedBeanDefinition(String name) throws BeansException {
		String beanName = transformedBeanName(name);
		// Efficiently check whether bean definition exists in this factory.
		if (!containsBeanDefinition(beanName) && getParentBeanFactory() instanceof ConfigurableBeanFactory) {
			return ((ConfigurableBeanFactory) getParentBeanFactory()).getMergedBeanDefinition(beanName);
		}
		// Resolve merged bean definition locally.
        // 当前的BeanFactory
		return getMergedLocalBeanDefinition(beanName);
	}
```

合并的核心代码：

```java
	protected RootBeanDefinition getMergedBeanDefinition(
			String beanName, BeanDefinition bd, @Nullable BeanDefinition containingBd)
			throws BeanDefinitionStoreException {

		synchronized (this.mergedBeanDefinitions) {
			RootBeanDefinition mbd = null;
			RootBeanDefinition previous = null;

			// Check with full lock now in order to enforce the same merged instance.
			if (containingBd == null) {
				mbd = this.mergedBeanDefinitions.get(beanName);
			}

			if (mbd == null || mbd.stale) {
				previous = mbd;
				if (bd.getParentName() == null) {
					// Use copy of given root bean definition.
					if (bd instanceof RootBeanDefinition) {
						mbd = ((RootBeanDefinition) bd).cloneBeanDefinition();
					}
					else {
						mbd = new RootBeanDefinition(bd);
					}
				}
				else {
					// Child bean definition: needs to be merged with parent.
					BeanDefinition pbd;
					try {
						String parentBeanName = transformedBeanName(bd.getParentName());
						if (!beanName.equals(parentBeanName)) {
							pbd = getMergedBeanDefinition(parentBeanName);
						}
						else {
							BeanFactory parent = getParentBeanFactory();
							if (parent instanceof ConfigurableBeanFactory) {
								pbd = ((ConfigurableBeanFactory) parent).getMergedBeanDefinition(parentBeanName);
							}
							else {
								throw new NoSuchBeanDefinitionException(parentBeanName,
										"Parent name '" + parentBeanName + "' is equal to bean name '" + beanName +
												"': cannot be resolved without a ConfigurableBeanFactory parent");
							}
						}
					}
					catch (NoSuchBeanDefinitionException ex) {
						throw new BeanDefinitionStoreException(bd.getResourceDescription(), beanName,
								"Could not resolve parent bean definition '" + bd.getParentName() + "'", ex);
					}
					// Deep copy with overridden values.
					mbd = new RootBeanDefinition(pbd);
					mbd.overrideFrom(bd);
				}

				// Set default singleton scope, if not configured before.
				if (!StringUtils.hasLength(mbd.getScope())) {
					mbd.setScope(SCOPE_SINGLETON);
				}

				// A bean contained in a non-singleton bean cannot be a singleton itself.
				// Let's correct this on the fly here, since this might be the result of
				// parent-child merging for the outer bean, in which case the original inner bean
				// definition will not have inherited the merged outer bean's singleton status.
				if (containingBd != null && !containingBd.isSingleton() && mbd.isSingleton()) {
					mbd.setScope(containingBd.getScope());
				}

				// Cache the merged bean definition for the time being
				// (it might still get re-merged later on in order to pick up metadata changes)
				if (containingBd == null && isCacheBeanMetadata()) {
					this.mergedBeanDefinitions.put(beanName, mbd);
				}
			}
			if (previous != null) {
				copyRelevantMergedBeanDefinitionCaches(previous, mbd);
			}
			return mbd;
		}
	}
```

## Bean Class 加载阶段

1. ClassLoader 类加载
2. Java Security 安全控制
3. ConfigurableBeanFactory 临时 ClassLoader（场景比较有限）

加载的核心代码代码：

```java
	public Class<?> resolveBeanClass(@Nullable ClassLoader classLoader) throws ClassNotFoundException {
		String className = getBeanClassName();
		if (className == null) {
			return null;
		}
		Class<?> resolvedClass = ClassUtils.forName(className, classLoader);
		this.beanClass = resolvedClass;
		return resolvedClass;
	}
```

最开始的 beanClass 实际上是一个 String 类型，然后通过 AppClassLoader 加载到 Class 对象并赋值给 beanClass 这个属性，这个属性本身是一个 Object 类型的：

```java
	@Nullable
	private volatile Object beanClass;
```

## 实例化

### 实例化前阶段

非主流生命周期-Bena 实例化前阶段

- InstantiationAwareBeanPostProcessor#postProcessBeforeInstantiation

首先我们给出这个接口的使用示例：

```java
public class BeanInstantiationLifecycleDemo {
    public static void main(String[] args) {
        DefaultListableBeanFactory beanFactory = new DefaultListableBeanFactory();
        // 添加BeanPostProcesssor实现
        beanFactory.addBeanPostProcessor(new MyInstantiationAwareBeanPostProcessor());
        // 基于XML资源BeanDefinitionReader 实现
        XmlBeanDefinitionReader xmlBeanDefinitionReader = new XmlBeanDefinitionReader(beanFactory);
        String location = "META-INF/dependency-lookup-context.xml";
        Resource resource = new ClassPathResource(location);
        EncodedResource encodedResource = new EncodedResource(resource, "UTF-8");
        int beanNumbers = xmlBeanDefinitionReader.loadBeanDefinitions(encodedResource);
        System.out.println("已加载的BeanDefinitiond的数量：" + beanNumbers);

        // 不需要合并BeanDefinition
        User user = beanFactory.getBean("user", User.class);
        System.out.println(user.toString());
        // 需要合并BeanDefinition
        SuperUser superUser = beanFactory.getBean("SuperUser", SuperUser.class);
        System.out.println(superUser.toString());
    }

    static class MyInstantiationAwareBeanPostProcessor implements InstantiationAwareBeanPostProcessor {
        @Override
        public Object postProcessBeforeInstantiation(Class<?> beanClass, String beanName) throws BeansException {
            if (ObjectUtils.nullSafeEquals("SuperUser",beanName) && SuperUser.class.equals(beanClass)) {
                // 把配置好的SuperUser Bean覆盖
                return new SuperUser();
            }
            return null; // 保持Spring IoC容器的实例化操作
        }
    }
}
```

通过源码分析，可以看到 postProcessBeforeInstantiation 方法被调用之后返回了这个对象。

```java
protected Object applyBeanPostProcessorsBeforeInstantiation(Class<?> beanClass, String beanName) {
		for (InstantiationAwareBeanPostProcessor bp : getBeanPostProcessorCache().instantiationAware) {
			Object result = bp.postProcessBeforeInstantiation(beanClass, beanName);
			if (result != null) {
				return result;
			}
		}
		return null;
	}
```

通过调用关系，不难看出，在实例化 Bean 的时候，如果上述的方法返回的不是一个空对象，就直接返回，不在进行实例化的操作。

```java
Object bean = resolveBeforeInstantiation(beanName, mbdToUse);
if (bean != null) {
    return bean;
}
```

### 实例化阶段

Spring 中实例化方式：

1. 传统实例化方式
   - 实例化策略 - InstantiationStrategy
2. 构造器注入

传统的方式可以在 AbstractAutowireCapableBeanFactory#instantiateBean

```java
beanInstance = getInstantiationStrategy().instantiate(mbd, beanName, this);
```

构造器注入，我们可以构造一个例子来进行测试：

```java
public class UserHolder {

    private final User user;

    @Override
    public String toString() {
        return "UserHolder{" +
                "user=" + user +
                '}';
    }

    public UserHolder(User user) {
        this.user = user;
    }
}
```

可以在之前的例子上稍作修改：

```java
public class BeanInstantiationLifecycleDemo {
    public static void main(String[] args) {
        DefaultListableBeanFactory beanFactory = new DefaultListableBeanFactory();
        // 添加BeanPostProcesssor实现
        beanFactory.addBeanPostProcessor(new MyInstantiationAwareBeanPostProcessor());
        // 基于XML资源BeanDefinitionReader 实现
        XmlBeanDefinitionReader xmlBeanDefinitionReader = new XmlBeanDefinitionReader(beanFactory);
        String[] locations = {"META-INF/dependency-lookup-context.xml","META-INF/bean-constructor-dependency-injection.xml"};
        int beanNumbers = xmlBeanDefinitionReader.loadBeanDefinitions(locations);
        System.out.println("已加载的BeanDefinitiond的数量：" + beanNumbers);
        // 不需要合并BeanDefinition
        User user = beanFactory.getBean("user", User.class);
        System.out.println(user.toString());
        // 需要合并BeanDefinition
        SuperUser superUser = beanFactory.getBean("SuperUser", SuperUser.class);
        System.out.println(superUser.toString());
        // 构造器注入式按照类型注入，底层resolveDependency
        UserHolder userHolder = beanFactory.getBean("userHolder", UserHolder.class);
        System.out.println(userHolder.toString());
    }

    static class MyInstantiationAwareBeanPostProcessor implements InstantiationAwareBeanPostProcessor {
        @Override
        public Object postProcessBeforeInstantiation(Class<?> beanClass, String beanName) throws BeansException {
            if (ObjectUtils.nullSafeEquals("SuperUser",beanName) && SuperUser.class.equals(beanClass)) {
                // 把配置好的SuperUser Bean覆盖
                return new SuperUser();
            }
            return null; // 保持Spring IoC容器的实例化操作
        }
    }
}
```

这里我们可以总结一下，Bean 的实例化主要有两种类型，并且使用构造器注入的时候，是按照类型来进行注入的，底层是使用的我们在依赖注入章节中介绍过的 resolveDependency 方法来实现的。

### Bean 实例化后阶段

对于 Spring Bean 实例化后阶段，我们可以理解为是 Bean 属性赋值（Populate）的判断：InstantiationAwareBeanPostProcessor#postProcessAfterInstantiation。可以结合 Bean 实例化前阶段一起对照查看：

```java
  static class MyInstantiationAwareBeanPostProcessor implements InstantiationAwareBeanPostProcessor {
        @Override
        public Object postProcessBeforeInstantiation(Class<?> beanClass, String beanName) throws BeansException {
            if (ObjectUtils.nullSafeEquals("SuperUser", beanName) && SuperUser.class.equals(beanClass)) {
                // 把配置好的SuperUser Bean覆盖
                return new SuperUser();
            }
            return null; // 保持Spring IoC容器的实例化操作
        }

        @Override
        public boolean postProcessAfterInstantiation(Object bean, String beanName) throws BeansException {
            if (ObjectUtils.nullSafeEquals("user", beanName) && User.class.equals(bean.getClass())) {
                User user = (User) bean;
                user.setId("33");
                user.setName("jjjjjj");
                // "user"对象不允许属性赋值（填入）（配置元信息 -> 属性值）
                return false;
            }
            return true;
        }
    }
```

这里相当于可以拦截掉所有的属性赋值，并且可以进行一些自定义的赋值，此时 Bean 的实例化已经完成了，但是属性赋值还没进行。

## 属性赋值前阶段

Bean 属性值信息的类：

- PropertyValues

Bean 属性赋值前回调

- Spring1.2-5.0：InstantiationAwareBeanPostProcessor#postProcessPropertyValues
- Spring 5.1：InstantiationAwareBeanPostProcessor#postProcessProperties

他们都是在 BeanFactory 赋值之前的回调操作，PropertyValues 就是从配置文件里面读入的值，这个方法的作用就是可以修改从配置文件里面读入的值，默认情况下不做任何修改。

```java
default PropertyValues postProcessPropertyValues(
			PropertyValues pvs, PropertyDescriptor[] pds, Object bean, String beanName) throws BeansException {

		return pvs;
	}
```

> 需要注意的是，这里的返回值是 null。

```java
default PropertyValues postProcessProperties(PropertyValues pvs, Object bean, String beanName)
			throws BeansException {

		return null;
	}
```

还在在我们之前的例子上稍作修改：

```java
       // 要注意如果postProcessAfterInstantiation返回的是false的话，这个方法不会被调用，因为相当于返回的Bean已经被替换了。
        @Override
        public PropertyValues postProcessProperties(PropertyValues pvs, Object bean, String beanName)
                throws BeansException {
            if (ObjectUtils.nullSafeEquals("userHolder", beanName) && UserHolder.class.equals(bean.getClass())) {
                // 假设<property name="number" value="1" />配置的话，那么在PropertyValues中就包含一个PropertyValues(number=1)
                final MutablePropertyValues propertyValues;
                if (pvs instanceof MutablePropertyValues) {
                    propertyValues = (MutablePropertyValues) pvs;
                } else {
                    propertyValues = new MutablePropertyValues();
                }
                // 等价于<property name="number" value="1" />
                propertyValues.addPropertyValue("number", "1");
                //
                if (propertyValues.contains("description")) {
                    // PropertyValue是不可变的
//                    PropertyValue description = propertyValues.getPropertyValue("description");
                    propertyValues.removePropertyValue("description");
                    propertyValues.addPropertyValue("description", "The user holder V2");
                }
                return propertyValues;
            }
            return null;
        }
```

这里我们演示了两种情况，一种是 number 这个属性本来是没有值的，通过这个 Api 的拦截，我们手动给他赋上了值，而 description 这个属性，是我们在 XML 文件中，定义好了属性值，从结果来看，这个属性值也成功的被修改了。

```xml
<bean id="userHolder" class="org.jyc.thinking.in.spring.bean.lifecycle.UserHolder" autowire="constructor">
<!--        <property name="number" value="1"/>-->
     <property name="description" value="The user holder" />
</bean>
```

修改后的 UserHolder 类：

```java
public class UserHolder {

    private final User user;

    private Integer number;

    private String description;

    public String getDescription() {
        return description;
    }

    public void setDescription(String description) {
        this.description = description;
    }

    public User getUser() {
        return user;
    }

    @Override
    public String toString() {
        return "UserHolder{" +
                "user=" + user +
                ", number=" + number +
                ", description='" + description + '\'' +
                '}';
    }

    public Integer getNumber() {
        return number;
    }

    public void setNumber(Integer number) {
        this.number = number;
    }


    public UserHolder(User user) {
        this.user = user;
    }
}

```

相应的源码：

![image-20210614105732908](./SpringFramework.assets/image-20210614105732908.png)

最后将准备好的 pvs 对象赋值给 BeanWrapper：

```java
if (pvs != null) {
	applyPropertyValues(beanName, mbd, bw, pvs);
}
```

## 初始化

### 接口回调阶段

Spring Aware 接口：

- BeanNameAware
- BeanClassLoaderAware
- BeanFactoryAware
- EnvironmentAware
- EmbeddedValueResolverAware
- ResourceLoaderAware
- ApplicationEventPublisherAware
- MessageSourceAware
- ApplicationContextAware

> 这里列出的顺序同时也是调用时候的顺序，这一点，源代码中也有体现：

```java
private void invokeAwareMethods(String beanName, Object bean) {
		if (bean instanceof Aware) {
			if (bean instanceof BeanNameAware) {
				((BeanNameAware) bean).setBeanName(beanName);
			}
			if (bean instanceof BeanClassLoaderAware) {
				ClassLoader bcl = getBeanClassLoader();
				if (bcl != null) {
					((BeanClassLoaderAware) bean).setBeanClassLoader(bcl);
				}
			}
			if (bean instanceof BeanFactoryAware) {
				((BeanFactoryAware) bean).setBeanFactory(AbstractAutowireCapableBeanFactory.this);
			}
		}
	}
```

另外一些相关的方法在 ApplicationContextAwareProcessor#invokeAwareInterfaces：

```java
private void invokeAwareInterfaces(Object bean) {
		if (bean instanceof EnvironmentAware) {
			((EnvironmentAware) bean).setEnvironment(this.applicationContext.getEnvironment());
		}
		if (bean instanceof EmbeddedValueResolverAware) {
			((EmbeddedValueResolverAware) bean).setEmbeddedValueResolver(this.embeddedValueResolver);
		}
		if (bean instanceof ResourceLoaderAware) {
			((ResourceLoaderAware) bean).setResourceLoader(this.applicationContext);
		}
		if (bean instanceof ApplicationEventPublisherAware) {
			((ApplicationEventPublisherAware) bean).setApplicationEventPublisher(this.applicationContext);
		}
		if (bean instanceof MessageSourceAware) {
			((MessageSourceAware) bean).setMessageSource(this.applicationContext);
		}
		if (bean instanceof ApplicationStartupAware) {
			((ApplicationStartupAware) bean).setApplicationStartup(this.applicationContext.getApplicationStartup());
		}
		if (bean instanceof ApplicationContextAware) {
			((ApplicationContextAware) bean).setApplicationContext(this.applicationContext);
		}
	}
```

但是第二部分的回调接口无法通过 BeanFacotry 的方式得到回调，我们需要对之前的代码进行一定的重构：

```java
public class BeanInstantiationLifecycleDemo {
    public static void main(String[] args) {
        executeBeanFactory();

        System.out.println("=============");

        executApplicationContext();
    }

    public static void executeBeanFactory() {
        DefaultListableBeanFactory beanFactory = new DefaultListableBeanFactory();
        // 方法一：添加BeanPostProcesssor实现InstantiationAwareBeanPostProcessor
        // 方法二：将MyInstantiationAwareBeanPostProcessor作为Bean注册
//        beanFactory.addBeanPostProcessor(new MyInstantiationAwareBeanPostProcessor());
        // 基于XML资源BeanDefinitionReader 实现
        XmlBeanDefinitionReader xmlBeanDefinitionReader = new XmlBeanDefinitionReader(beanFactory);
        String[] locations = {"META-INF/dependency-lookup-context.xml", "META-INF/bean-constructor-dependency-injection.xml"};
        int beanNumbers = xmlBeanDefinitionReader.loadBeanDefinitions(locations);
        System.out.println("已加载的BeanDefinitiond的数量：" + beanNumbers);
        // 不需要合并BeanDefinition
        User user = beanFactory.getBean("user", User.class);
        System.out.println(user.toString());
        // 需要合并BeanDefinition
        SuperUser superUser = beanFactory.getBean("SuperUser", SuperUser.class);
        System.out.println(superUser.toString());
        // 构造器注入式按照类型注入，底层resolveDependency
        UserHolder userHolder = beanFactory.getBean("userHolder", UserHolder.class);
        System.out.println(userHolder.toString());
    }

    public static void executApplicationContext() {
        ClassPathXmlApplicationContext applicationContext = new ClassPathXmlApplicationContext();
        String[] locations = {"META-INF/dependency-lookup-context.xml", "META-INF/bean-constructor-dependency-injection.xml"};
        applicationContext.setConfigLocations(locations);
        applicationContext.refresh();
        User user = applicationContext.getBean("user", User.class);
        System.out.println(user.toString());
        SuperUser superUser = applicationContext.getBean("SuperUser", SuperUser.class);
        System.out.println(superUser.toString());
        UserHolder userHolder = applicationContext.getBean("userHolder", UserHolder.class);
        System.out.println(userHolder.toString());
        applicationContext.close();
    }
}
```

在 XML 文件中，注入 MyInstantiationAwareBeanPostProcessor：

```xml
<bean class="org.jyc.thinking.in.spring.bean.lifecycle.MyInstantiationAwareBeanPostProcessor" />
```

我们可以在 UserHolder 中实现这些接口，进行观察：

```java
public class UserHolder implements BeanNameAware, BeanClassLoaderAware, BeanFactoryAware, EnvironmentAware {

    private final User user;

    private Integer number;

    private String description;

    private ClassLoader classLoader;

    private BeanFactory beanFactory;

    private String beanName;

    private Environment environment;

    public String getDescription() {
        return description;
    }

    public void setDescription(String description) {
        this.description = description;
    }

    public User getUser() {
        return user;
    }

    @Override
    public String toString() {
        return "UserHolder{" +
                "user=" + user +
                ", number=" + number +
                ", description='" + description + '\'' +
                ", beanName='" + beanName + '\'' +
                '}';
    }

    public Integer getNumber() {
        return number;
    }

    public void setNumber(Integer number) {
        this.number = number;
    }


    public UserHolder(User user) {
        this.user = user;
    }

    @Override
    public void setBeanClassLoader(ClassLoader classLoader) {
        this.classLoader = classLoader;
    }

    @Override
    public void setBeanFactory(BeanFactory beanFactory) throws BeansException {
        this.beanFactory = beanFactory;
    }

    @Override
    public void setBeanName(String name) {
        this.beanName = name;
    }

    @Override
    public void setEnvironment(Environment environment) {
        this.environment = environment;
    }
}
```

不难发现，通过 BeanFacotry 的方式，无法获取到 EnvironmentAware 对象的回调，而 ApplicationContext 则可以，这是因为在 AbstractApplicationContext#prepareBeanFactory 中，BeanFactory 注册了 ApplicationContextAwareProcessor 这个接口：

```java
beanFactory.addBeanPostProcessor(new ApplicationContextAwareProcessor(this));
```

而我们前面提到过，第二部分的接口的回调，需要执行 ApplicationContextAwareProcessor#invokeAwareInterfaces 方法，而 ApplicationContextAwareProcessor 又是一个非 public 的类，因此，在我们创建的 BeanFactory 无法操作这个类。总来的来说，通过 BeanFactory 可以获取到 BeanNameAware、BeanClassLoaderAware、BeanFactoryAware 这三个接口的回调，而如果使用 AppliactionContext 来进行操作，就可以获取到更多的回调，这也从另一个角度说明了 AppliacitonContext 和 BeanFactory 的区别。

### 初始化前阶段

方法回调：

- BeanPostProcessor#postProcessBeforeInitialization

因为 InstantiationAwareBeanPostProcessor 继承了 BeanPostProcessor，因此我们还是调整 MyInstantiationAwareBeanPostProcessor 的方法来进行观察：

```java
	@Override
    public Object postProcessBeforeInitialization(Object bean, String beanName) throws BeansException {
        if (ObjectUtils.nullSafeEquals("userHolder", beanName) && UserHolder.class.equals(bean.getClass())) {
            UserHolder userHolder = (UserHolder) bean;
            userHolder.setDescription("The user holder V3");
            return userHolder;
        }
        return null;
    }
```

为了跟前面加以区别，这里我们增加一个调用的示例：

```java
public class BeanInitilzationLifecycleDemo {
    public static void main(String[] args) {
        executeBeanFactory();
    }

    public static void executeBeanFactory() {
        DefaultListableBeanFactory beanFactory = new DefaultListableBeanFactory();
        // 方法一：添加BeanPostProcesssor实现InstantiationAwareBeanPostProcessor
        // 方法二：将MyInstantiationAwareBeanPostProcessor作为Bean注册
        beanFactory.addBeanPostProcessor(new MyInstantiationAwareBeanPostProcessor());
        // 基于XML资源BeanDefinitionReader 实现
        XmlBeanDefinitionReader xmlBeanDefinitionReader = new XmlBeanDefinitionReader(beanFactory);
        String[] locations = {"META-INF/dependency-lookup-context.xml", "META-INF/bean-constructor-dependency-injection.xml"};
        int beanNumbers = xmlBeanDefinitionReader.loadBeanDefinitions(locations);
        System.out.println("已加载的BeanDefinitiond的数量：" + beanNumbers);
        // 不需要合并BeanDefinition
        User user = beanFactory.getBean("user", User.class);
        System.out.println(user.toString());
        // 需要合并BeanDefinition
        SuperUser superUser = beanFactory.getBean("SuperUser", SuperUser.class);
        System.out.println(superUser.toString());
        // 构造器注入式按照类型注入，底层resolveDependency
        UserHolder userHolder = beanFactory.getBean("userHolder", UserHolder.class);
        System.out.println(userHolder.toString());
    }
}
```

可以看到 userHolder 的 description 属性成功的变成了 v3，相关的源码的实现在 AbstractAutowireCapableBeanFactory#pplyBeanPostProcessorsBeforeInitialization：

```java
	@Override
	public Object applyBeanPostProcessorsBeforeInitialization(Object existingBean, String beanName)
			throws BeansException {

		Object result = existingBean;
		for (BeanPostProcessor processor : getBeanPostProcessors()) {
			Object current = processor.postProcessBeforeInitialization(result, beanName);
			if (current == null) {
				return result;
			}
             // 可能返回的是一个代理对象，并不是原有的对象
			result = current;
		}
		return result;
	}
```

### 初始化阶段

在之前，我们有提到过 Bean 初始化操作：

- @PostConstruct 标注方法
- 实现 InitializingBean 接口的 afterPropertiesSet()方法
- 自定义初始化方法

> @PostConstruct 标注方法需要注解驱动，因为这种方式需要依赖于 ApplicationContext 的，并且所依赖的 ApplicationContext 是需要有注解驱动能力的。

我们在 UserHolder 中添加它的初始化方法：

```java
 /**
     * 依赖于注解驱动，当前场景：BeanFactory，因此直接运行，并不会执行
     */
    @PostConstruct
    public void initPostConstruct() {
        this.description = "The user holder V4";
        System.out.println("initPostConstruct() = " + description);
    }

    @Override
    public void afterPropertiesSet() throws Exception {
        this.description = "The user holder V5";
        System.out.println("afterPropertiesSet() = " + description);
    }

    public void init() {
        this.description = "The user holder V6";
        System.out.println("init() = " + description);
    }
```

这里因为我们是 BeanFactory 的场景，因此需要手动添加：

```java
 beanFactory.addBeanPostProcessor(new CommonAnnotationBeanPostProcessor());
```

相应的源码在 AbstractAutowireCapableBeanFactory#invokeInitMethods 方法当中：

```java
protected void invokeInitMethods(String beanName, Object bean, @Nullable RootBeanDefinition mbd)
			throws Throwable {
		// afterPropertiesSet方法：
		boolean isInitializingBean = (bean instanceof InitializingBean);
		if (isInitializingBean && (mbd == null || !mbd.isExternallyManagedInitMethod("afterPropertiesSet"))) {
			if (logger.isTraceEnabled()) {
				logger.trace("Invoking afterPropertiesSet() on bean with name '" + beanName + "'");
			}
			if (System.getSecurityManager() != null) {
				try {
					AccessController.doPrivileged((PrivilegedExceptionAction<Object>) () -> {
						((InitializingBean) bean).afterPropertiesSet();
						return null;
					}, getAccessControlContext());
				}
				catch (PrivilegedActionException pae) {
					throw pae.getException();
				}
			}
			else {
				((InitializingBean) bean).afterPropertiesSet();
			}
		}
		// 自定义初始化方法
		if (mbd != null && bean.getClass() != NullBean.class) {
			String initMethodName = mbd.getInitMethodName();
			if (StringUtils.hasLength(initMethodName) &&
					!(isInitializingBean && "afterPropertiesSet".equals(initMethodName)) &&
					!mbd.isExternallyManagedInitMethod(initMethodName)) {
				invokeCustomInitMethod(beanName, bean, mbd);
			}
		}
	}
```

### 初始化后阶段

方法的回调：

- BeanPostProcessor#postProcessAfterInitialization

还是对我们的 MyInstantiationAwareBeanPostProcessor 进行添加：

```java
 	@Override
    public Object postProcessAfterInitialization(Object bean, String beanName) throws BeansException {
        if (ObjectUtils.nullSafeEquals("userHolder", beanName) && UserHolder.class.equals(bean.getClass())) {
            UserHolder userHolder = (UserHolder) bean;
            userHolder.setDescription("The user holder V7");
            return userHolder;
        }
        return null;
    }
```

总的来说，关于 Bean 的初始化操作，总共可以分为下面几个阶段：

```java
	protected Object initializeBean(String beanName, Object bean, @Nullable RootBeanDefinition mbd) {
		if (System.getSecurityManager() != null) {
			AccessController.doPrivileged((PrivilegedAction<Object>) () -> {
				invokeAwareMethods(beanName, bean);
				return null;
			}, getAccessControlContext());
		}
		else {
            // 接口回调
			invokeAwareMethods(beanName, bean);
		}

		Object wrappedBean = bean;
		if (mbd == null || !mbd.isSynthetic()) {
            // 初始化前方法
			wrappedBean = applyBeanPostProcessorsBeforeInitialization(wrappedBean, beanName);
		}

		try {
            // 初始化方法
			invokeInitMethods(beanName, wrappedBean, mbd);
		}
		catch (Throwable ex) {
			throw new BeanCreationException(
					(mbd != null ? mbd.getResourceDescription() : null),
					beanName, "Invocation of init method failed", ex);
		}
		if (mbd == null || !mbd.isSynthetic()) {
            // 初始化后方法
			wrappedBean = applyBeanPostProcessorsAfterInitialization(wrappedBean, beanName);
		}

		return wrappedBean;
	}
```

### 初始化完成阶段

方法回调：

- SmartInitializingSingleton#afterSingletonsInstantiated

同样的，还是操作 Userholder 类：

```java
	@Override
    public void afterSingletonsInstantiated() {
        this.description = "The user holder V8";
        System.out.println("afterSingletonsInstantiated() = " + description);

    }
```

直接去运行，发现并没有打印出我们预期的结果，这是因为这个方法调用的地方在 DefaultListableBeanFactory#preInstantiateSingletons，而这个方法需要显示的调用才会执行：

```java
 // SmartInitializingSingleton 通常在Spring AppliactionContext场景使用
 // preInstantiateSingletons将已注册的BeanDefinition初始化成Spring Bean
 beanFactory.preInstantiateSingletons();
```

在 AbstractApplicationContext#finishBeanFactoryInitialization 方法中，我们可以看到这里就调用了 preInstantiateSingletons 方法：

```java
protected void finishBeanFactoryInitialization(ConfigurableListableBeanFactory beanFactory) {
		// Instantiate all remaining (non-lazy-init) singletons.
		beanFactory.preInstantiateSingletons();
	}
```

提供这个方法的主要原因是之前的 BeanPostProcessor 接口提供的回调，可能 Bean 会存在初始化不完全的情况，使用这个方法的时候就不用担心有 Bean 初始化不完全的情况发生。

## 销毁阶段

### 销毁前阶段

方法回调：

- DestructionAwareBeanPostProcessor#postProcessBeforeDestruction

实现一下这个接口：

```java
public class MyDestructionAwareBeanPostProcessor implements DestructionAwareBeanPostProcessor {
    @Override
    public void postProcessBeforeDestruction(Object bean, String beanName) throws BeansException {
        if (ObjectUtils.nullSafeEquals("userHolder", beanName) && UserHolder.class.equals(bean.getClass())) {
            UserHolder userHolder = (UserHolder) bean;
            userHolder.setDescription("The user holder V9");
        }
    }
}
```

关于 Bean 生命周期的完整的演示示例：

```java
public class BeanLifeCycleDemo {
    public static void main(String[] args) {
        DefaultListableBeanFactory beanFactory = new DefaultListableBeanFactory();
        // 方法一：添加BeanPostProcesssor实现InstantiationAwareBeanPostProcessor
        // 方法二：将MyInstantiationAwareBeanPostProcessor作为Bean注册
        beanFactory.addBeanPostProcessor(new MyInstantiationAwareBeanPostProcessor());
        beanFactory.addBeanPostProcessor(new CommonAnnotationBeanPostProcessor());
        // 添加MyDestructionAwareBeanPostProcessor执行销毁前回调
        beanFactory.addBeanPostProcessor(new MyDestructionAwareBeanPostProcessor());
        // 基于XML资源BeanDefinitionReader 实现
        XmlBeanDefinitionReader xmlBeanDefinitionReader = new XmlBeanDefinitionReader(beanFactory);
        String[] locations = {"META-INF/dependency-lookup-context.xml", "META-INF/bean-constructor-dependency-injection.xml"};
        int beanNumbers = xmlBeanDefinitionReader.loadBeanDefinitions(locations);
        System.out.println("已加载的BeanDefinitiond的数量：" + beanNumbers);
        beanFactory.preInstantiateSingletons();
        // 不需要合并BeanDefinition
        User user = beanFactory.getBean("user", User.class);
        System.out.println(user.toString());
        // 需要合并BeanDefinition
        SuperUser superUser = beanFactory.getBean("SuperUser", SuperUser.class);
        System.out.println(superUser.toString());
        // 构造器注入式按照类型注入，底层resolveDependency
        UserHolder userHolder = beanFactory.getBean("userHolder", UserHolder.class);
        // SmartInitializingSingleton 通常在Spring AppliactionContext场景使用
        System.out.println(userHolder.toString());

        beanFactory.destroyBean("userHolder", userHolder);
        // Bean销毁并不意味这Bean垃圾回收了
        System.out.println(userHolder.toString());
    }
}
```

> 特别需要注意的是，这里的销毁并不是这个对象被 GC 掉了，GC 和 Bean 的销毁是两个不同的概念。

### 销毁阶段

Bean 销毁（Destory）：

- @PreDestory 标注方法
- 实现 DisposableBean 接口的 destory()方法
- 自定义销毁方法

```java
	@PreDestroy
    public void preDestory() {
        this.description = "The user holder V10";
        System.out.println("PreDestroy() = " + description);
    }

    @Override
    public void destroy() throws Exception {
        this.description = "The user holder V11";
        System.out.println("PreDestroy() = " + description);
    }

    public void doDestory() {
        this.description = "The user holder V12";
        System.out.println("PreDestroy() = " + description);
    }
```

在 XML 中指定自定义的销毁方法：

```xml
<bean id="userHolder" class="org.jyc.thinking.in.spring.bean.lifecycle.UserHolder" autowire="constructor" init-method="init" destroy-method="doDestory">
<!--        <property name="number" value="1"/>-->
        <property name="description" value="The user holder" />
 </bean>
```

在 BeanFactory 场景下还是需要手动进行调用，而在 ApplicationContext 中，是会自动调用的：

```java
beanFactory.destroyBean("userHolder", userHolder);
```

## Bean 垃圾收集

Bean 垃圾回收（GC）的过程：

1. 关闭 Spring 容器（应用上下文）
2. 执行 GC
3. Spring Bean 覆盖的 finalize()方法被回调

首先在 UserHolder 中重写 finalize()方法：

```java
@Override
protected void finalize() throws Throwable {
    System.out.println("UserHolder is finalized ...");
    super.finalize();
}
```

然后执行销毁方法：

```java
   		// 销毁BeanFactory中的单例Bean
        beanFactory.destroySingletons();
        // 强制GC
        System.gc();
        // 等待一段时间
        try {
            Thread.sleep(3000);
        } catch (InterruptedException exception) {
            exception.printStackTrace();
        }

        System.gc();
```

## 面试题

### BeanPostProcess 使用场景有哪些？

BeanPostProcess 提供了 Spring Bean 初始化前和初始化后的生命周期回调，分别对应 postProcessBeforeInitialization 以及 postProcessAfterInitialization 方法，允许对关心的 Bean 进行扩展，甚至是替换，

其中 ApplicationContext 相关的 Aware 回调也是基于 BeanPostProcess 实现，即 ApplicationContextAwareProcessor。

### BeanFactoryPostProcess 与 BeanPostProcess 的区别

BeanFactroyPostProcessor 是 Spring BeanFacrtory（实际为 ConfigurableListableBeanFactory）的后置处理器，用于扩展 BeanFacotry，或通过 BeanFactory 进行依赖查找和依赖注入。

BeanFactroyPostProcessor 必须有 Spring ApplicationContext 执行，BeanFactory 无法与其直接交互。而 BeanPostProcess 直接与 BeanFactory 关联，属于 N 对 1 的关系。

### BeanFactory 是怎样处理 Bean 生命周期？

BeanFactory 的默认实现为 DefaultListableBeanFactory，其中 Bean 生命周期与方法映射如下：

- BeanDefinition 注册阶段 - regsiterBeanDefinition
- BeanDefinition 合并阶段 - getMergedBeanDefinition
- Bean 实例化前阶段 - resolveBeforeInstantiation
- Bean 实例化阶段 - createBeanInstance
- Bean 实例化后阶段- populateBean
- Bean 属性赋值前阶段 - populateBean
- Bean 属性赋值阶段 - populateBean
- Bean Aware 接口回调阶段 - initializeBean
- Bean 初始化前阶段- initializeBean
- Bean 初始化阶段- initializeBean
- Bean 初始化后阶段- initializeBean
- Bean 初始化完成阶段 - preInstantiateSingtons
- Bean 销毁前阶段- destoryBean
- Bean 销毁阶段 - destoryBean

# Spring 配置元信息

配置元信息主要可以分为以下五个方面：

1. Spring Bean 配置元信息 - BeanDefinition
2. Spring Bean 属性元信息 - PropertyValues
3. Spring 容器配置元信息
4. Spring 外部化配置元信息 - PropertySource
5. Spring Profile 元信息 - @Profile

## Spring Bean 配置元信息

Bean 的配置元信息 - BeanDefinition 主要包括了：

- GenericBeanDefinition：通用型 BeanDefinition
- RootBeanDefinition：无 parent 的 BeanDefinition 或者合并后 BeanDefinition
- AnnotatedBeanDefinition：注解标注的 BeanDefinition

> AnnotatedBeanDefinition 中的 AnnotationMetadata 有两种具体的实现，StandardAnnotationMetadata 是基于 Java 注解实现的，SimpleAnnotationMetadata 是基于 ASM 实现的。

## Spring Bean 属性元信息

1. Bean 属性元信息 - PropertyValues
   - 可修改实现 - MutablePropertyValues
   - 元素成员 - PropertyValue
2. Bean 属性上下文存储 - AttributeAccessor
3. Bean 元信息元素 - BeanMetadataElement

其中第一种我们已经见过很多次了，这里主要演示第二种和第三种。

```java
public class BeanConfigurationMetadataDemo {
    public static void main(String[] args) {
        // BeanDefinition 的定义（声明）
        BeanDefinitionBuilder beanDefinitionBuilder = BeanDefinitionBuilder.genericBeanDefinition(User.class);
        beanDefinitionBuilder.addPropertyValue("name", "jycoder");
        // 获取AbstractBeanDefinition
        AbstractBeanDefinition beanDefinition = beanDefinitionBuilder.getBeanDefinition();
        // 声明BeanDefinition
        // 附件属性(不影响Bean 实例化、属性赋值、初始化)
        beanDefinition.setAttribute("name", "jiyongchao");
        // 当前BeanDefinition来自何方,也是起存储的作用
        beanDefinition.setSource(BeanConfigurationMetadataDemo.class);
        DefaultListableBeanFactory beanFactory = new DefaultListableBeanFactory();
        beanFactory.addBeanPostProcessor(new BeanPostProcessor() {
            @Override
            public Object postProcessAfterInitialization(Object bean, String beanName) throws BeansException {
                if (ObjectUtils.nullSafeEquals("user", beanName) && User.class.equals(bean.getClass())) {
                    BeanDefinition bd = beanFactory.getBeanDefinition(beanName);
                    if (BeanConfigurationMetadataDemo.class.equals(bd.getSource())) { // 通过source来判断
                        // TODO
                    }
                    // 属性（存储）上下文
                    String name = (String) bd.getAttribute("jiyongchao"); // 这里的name就是jiyongchao
                    User user = (User) bean;
                    user.setName(name);
                }
                return null;
            }
        });
        beanFactory.registerBeanDefinition("user", beanDefinition);

        User user = beanFactory.getBean("user", User.class);
        System.out.println(user);
    }
}
```

## Spring 容器配置元信息

Spring XML 配置元信息 - Beans 元素相关

| Beans 元素属性              | 默认直       | 使用场景                                                               |
| --------------------------- | ------------ | ---------------------------------------------------------------------- |
| profile                     | null（留空） | Spring Profiles 配置值                                                 |
| default-lazt-init           | default      | 当 outter beans "default-lazy-init"属性存在时，继承该值，否则为"false" |
| default-merge               | default      | 当 outter beans "default-merge"属性存在时，继承该值，否则为"false"     |
| default-autowire            | default      | 当 outter beans "default-autowire"属性存在时，继承该值，否则为"false"  |
| default-autowire-candidates | null（留空） | 默认 Spring Beans 名称 pattern                                         |
| default-init-method         | null（留空） | 默认 Spring Beans 自定义初始化方法                                     |
| default-destory-method      | null（留空） | 默认 Spring Beans 自定义销毁方法                                       |

> outter beans 指的是在 XML 文件中通过 import 导入资源的方法注册 Bean，导入方就是外部，被导入方就是内部。

Spring XML 配置元信息 - 应用上下文

| XML 元素                         | 使用场景                               |
| -------------------------------- | -------------------------------------- |
| <context:annotation-config />    | 激活 Spring 注解驱动                   |
| <context:componenet-scan />      | Spring@Component 以及自定义注解扫描    |
| <context:load-time-weaver />     | 激活 Spring LoadTimeWeaver             |
| <context:mbean-export />         | 暴露 Spring Beans 作为 JMX Beans       |
| <context:mbean-server />         | 将当前平台作为 MBeanServer             |
| <context:property-placeholder /> | 加载外部化配置资源作为 Spring 属性配置 |
| <context:property-override />    | 利用外部化配置资源覆盖 Spring 属性值   |

> mbean：Java Management Extensions

关于 Beans 的元素相关的配置可以在`BeanDefinitionParserDelegate#populateDefaults`中看到。

## 基于 XML 资源装载 Spring Bean 配置元信息

Spring Bean 配置元信息

| XML 元素         | 使用场景                                      |
| ---------------- | --------------------------------------------- |
| <beans:beans />  | 单 XML 资源下的多个 Spring Beans 配置         |
| <beans:bean />   | 单个 Spring Bean 定义（BeanDefinition）配置   |
| <beans:alias />  | 为 Spring Bean 定义（BeanDefinition）映射别名 |
| <beans:import /> | 加载外部 Spring XML 配置资源                  |

> 通常情况下我们会使用默认的 namespace，这里使用 beans 来更加明确的说明，这里的底层实现都是 XmlBeanDefinitionReader。

装在的核心方法在 XmlBeanDefinitionReader#registerBeanDefinitions：

```java
public int registerBeanDefinitions(Document doc, Resource resource) throws BeanDefinitionStoreException {
		BeanDefinitionDocumentReader documentReader = createBeanDefinitionDocumentReader();
		int countBefore = getRegistry().getBeanDefinitionCount();
		documentReader.registerBeanDefinitions(doc, createReaderContext(resource));
		return getRegistry().getBeanDefinitionCount() - countBefore;
	}
```

## 基于 Properties 资源装载 Spring Bean 配置元信息

Spring Bean 配置元信息

| Properties 属性名 | 使用场景                        |
| ----------------- | ------------------------------- |
| (class)           | Bean 类全称限定名               |
| (abstract)        | 是否为抽象的 BeanDefinition     |
| (parent)          | 指定 parent BeanDefinition 名称 |
| (lazy-init)       | 是否为延迟初始化                |
| (ref)             | 应用其他 Bean 的名称            |
| (scope)           | 设置 Bean 的 scope 属性         |
| ${n}              | n 表示第 n+1 个构造器参数       |

> 底层实现：PropertiesBeanDefinitionReader

接下来我们定义一个 properties 文件：

```java
# User BeanDefinition 定义
user.(class) = org.jyc.thinking.in.spring.ioc.overview.dependency.domain.User
user.id = 1
user.name = jiyongchao
user.city = HANGZHOU
```

尝试获取解析：

```java
public class PropertiesBeanDefinitionReaderDemo {
    public static void main(String[] args) {
        DefaultListableBeanFactory beanFactory = new DefaultListableBeanFactory();
        PropertiesBeanDefinitionReader beanDefinitionReader = new PropertiesBeanDefinitionReader(beanFactory);
        String location = "classpath:/META-INF/users-config-definitions.properties";
        // 默认通过ISO-8859-1
        ResourceLoader resourceLoader = new DefaultResourceLoader();
        // 通过指定的Classpath获取Resource对象
        Resource resource = resourceLoader.getResource(location);
        // 转换成带字符编码的EncodedResource对象
        EncodedResource encodedResource = new EncodedResource(resource, "UTF-8");
        int i = beanDefinitionReader.loadBeanDefinitions(encodedResource);
        System.out.printf("已加载%d 个BeanDefinition\n", i);

        User user = beanFactory.getBean(User.class);
        System.out.println(user);
    }
}
```

相关核心代码在 PropertiesBeanDefinitionReader#loadBeanDefinitions：

```java
	public int loadBeanDefinitions(EncodedResource encodedResource, @Nullable String prefix)
			throws BeanDefinitionStoreException {

		if (logger.isTraceEnabled()) {
			logger.trace("Loading properties bean definitions from " + encodedResource);
		}

		Properties props = new Properties();
		try {
			try (InputStream is = encodedResource.getResource().getInputStream()) {
				if (encodedResource.getEncoding() != null) {
					getPropertiesPersister().load(props, new InputStreamReader(is, encodedResource.getEncoding()));
				}
				else {
					getPropertiesPersister().load(props, is);
				}
			}

			int count = registerBeanDefinitions(props, prefix, encodedResource.getResource().getDescription());
			if (logger.isDebugEnabled()) {
				logger.debug("Loaded " + count + " bean definitions from " + encodedResource);
			}
			return count;
		}
		catch (IOException ex) {
			throw new BeanDefinitionStoreException("Could not parse properties from " + encodedResource.getResource(), ex);
		}
	}
```

> 使用 properties 的方式读取 BeanDefinition 的时候，如果出现 Bean 重复定义的情况，Spring 会忽略后面定义的 Bean 的相关信息。

## 基于 Java 注解的 Spring Bean 配置元信息

Spring 模式注解：

| Spring 注解    | 场景说明           | 起始版本 |
| -------------- | ------------------ | -------- |
| @Repository    | 数据仓储模式注解   | 2.0      |
| @Component     | 通用组件模式注解   | 2.5      |
| @Service       | 服务模式注解       | 2.5      |
| @Controller    | Web 控制器模式注解 | 2.5      |
| @Configuration | 配置类模式注解     | 3.0      |

由于注解是不能集成的，所以采用元注解（元标注的方式来实现），其他注解都可以看成是`@Component`的"派生"注解。

Spring Bean 依赖注入注解：

| Spring 注解 | 场景说明                              | 起始版本 |
| ----------- | ------------------------------------- | -------- |
| @Autowired  | Bean 依赖注入，支持多种依赖查找的方式 | 2.5      |
| @Qualifier  | 细粒度的@Autowired 依赖查找           | 2.5      |

| Java 注解 | 场景说明         | 起始版本 |
| --------- | ---------------- | -------- |
| @Resource | 类似于@Autowired | 2.5      |
| @Inject   | 类似于@Autowired | 2.5      |

Spring Bean 条件装配注解：

| Spring 注解  | 场景说明       | 起始版本 |
| ------------ | -------------- | -------- |
| @Profile     | 配置化条件装配 | 3.1      |
| @Conditional | 编程条件装配   | 4.0      |

我们可以看一下@Profile 注解的@Conditional：

```java
class ProfileCondition implements Condition {

	@Override
	public boolean matches(ConditionContext context, AnnotatedTypeMetadata metadata) {
		MultiValueMap<String, Object> attrs = metadata.getAllAnnotationAttributes(Profile.class.getName());
		if (attrs != null) {
			for (Object value : attrs.get("value")) {
				if (context.getEnvironment().acceptsProfiles(Profiles.of((String[]) value))) {
					return true;
				}
			}
			return false;
		}
		return true;
	}

}
```

最后是 Spring Bean 声明周期回调注解：

| Spring 注解    | 场景说明                  | 起始版本 |
| -------------- | ------------------------- | -------- |
| @PostConstruct | 替换 XML 标签或者实现接口 | 2.5      |
| @PreDestory    | 替换 XML 标签或者实现接口 | 2.5      |

## Spring Bean 配置元信息底层实现

Spring BeanDefinition 解析与注册的方式：

| 实现场景   | 实现类                         | 起始版本 |
| ---------- | ------------------------------ | -------- |
| XML 资源   | XmlBeanDefinitionReader        | 1.0      |
| Properties | PropertiesBeanDefinitionReader | 1.0      |
| Java 注解  | AnnotatedBeanDefinitionReader  | 3.0      |

> 需要注意的是 AnnotatedBeanDefinitionReader 与 BeanDefinition 并没有任何直接的关系，而 XmlBeanDefinitionReader 和 PropertiesBeanDefinitionReader 都继承了 AbstractBeanDefinitionReader。

### XML 资源的方式

Spring XML 资源 BeanDefinition 解析与注册：

- 核心 API - XmlBeanDefinitionReader
- 底层 - BeanDefinitionDocumentReader
  - XML 解析 - Java DOM Level 3 API
  - BeanDefinition 解析 - BeanDefinitionParserDelegate
  - BeanDefinition 注册 - BeanDefinitionRegistry

> BeanDefinitionDocumentReader 有且仅有一个实现，DefaultBeanDefinitionDocumentReader，它里面的 preProcessXml 和 postProcessXml 方法都是空实现，可以让我们在加载 XML 资源的前后做一些自定义的操作，使用的时候只需要继承 DefaultBeanDefinitionDocumentReader，然后设置 XmlBeanDefinitionReader 所使用的加载类。

```java
private Class<? extends BeanDefinitionDocumentReader> documentReaderClass =
			DefaultBeanDefinitionDocumentReader.class;
```

### Properties 资源的方式

Spring Properties 资源 BeanDefinition 解析与注册：

- 核心 API - PropertiesBeanDefinitionReader
  - 资源
    - 字节流 - Resource
    - 字符流 - EncodedResource
  - 底层
    - 存储 - java.util.Properties
    - BeanDefinition 解析 - API 内部实现
    - BeanDefinition 注册 - BeanDefinitionRegistry

> 通过这种方式装在的 Bean 的名称就是"."之前的字符。

### Java 注解的方式

Spring Java 注册 BeanDefintiion 解析与注册：

- 核心 API - AnnotatedBeanDefinitionReader
  - 资源
    - 类对象 - java.lang.Class
  - 底层
    - 条件评估 - ConditionEvaluator
    - Bean 范围解析 - ScopeMetadataResolver
    - BeanDefinition 解析 - 内部 API 实现
    - BeanDefinition 处理 - AnnotationConfigUtils.processCommonDefinitionAnnotations
    - BeanDefinition 注册 - BeanDefinitionRegistry

实现的核心源代码：

```java
private <T> void doRegisterBean(Class<T> beanClass, @Nullable String name,
			@Nullable Class<? extends Annotation>[] qualifiers, @Nullable Supplier<T> supplier,
			@Nullable BeanDefinitionCustomizer[] customizers) {

		AnnotatedGenericBeanDefinition abd = new AnnotatedGenericBeanDefinition(beanClass);
		if (this.conditionEvaluator.shouldSkip(abd.getMetadata())) {
			return;
		}

		abd.setInstanceSupplier(supplier);
		ScopeMetadata scopeMetadata = this.scopeMetadataResolver.resolveScopeMetadata(abd);
		abd.setScope(scopeMetadata.getScopeName());
		String beanName = (name != null ? name : this.beanNameGenerator.generateBeanName(abd, this.registry));
		// 如果Bean上面有@Lazy或者@Primary等等，这个方法会把相关的信息赋值给BeanDefinition
		AnnotationConfigUtils.processCommonDefinitionAnnotations(abd);
		if (qualifiers != null) {
			for (Class<? extends Annotation> qualifier : qualifiers) {
				if (Primary.class == qualifier) {
					abd.setPrimary(true);
				}
				else if (Lazy.class == qualifier) {
					abd.setLazyInit(true);
				}
				else {
					abd.addQualifier(new AutowireCandidateQualifier(qualifier));
				}
			}
		}
		if (customizers != null) {
			for (BeanDefinitionCustomizer customizer : customizers) {
				customizer.customize(abd);
			}
		}

		BeanDefinitionHolder definitionHolder = new BeanDefinitionHolder(abd, beanName);
		definitionHolder = AnnotationConfigUtils.applyScopedProxyMode(scopeMetadata, definitionHolder, this.registry);
		BeanDefinitionReaderUtils.registerBeanDefinition(definitionHolder, this.registry);
	}
```

## 基于 XML 资源装载 Spring 容器配置元信息

Spring IoC 容器相关 XML 配置：

| 命名空间 | 所属模块       | Schema 资源 URL                                                        |
| -------- | -------------- | ---------------------------------------------------------------------- |
| beans    | spring-beans   | http://www.springframework.org/schema/beans/spring-beans.xsd           |
| context  | spring-context | http://www.springframework.org/schema/context/beans/spring-context.xsd |
| aop      | spring-aop     | http://www.springframework.org/schema/aop/spring-aop.xsd               |
| tx       | spring-tx      | http://www.springframework.org/schema/tx/spring-tx.xsd                 |
| util     | spring-util    | http://www.springframework.org/schema/util/spring-util.xsd             |
| tool     | spring-beans   | http://www.springframework.org/schema/tool/spring-tool.xsd             |

> 如果需要支持事务，需要单独引入 spring-tx。

## 基于 Java 注解配置 Spring 容器配置元信息

Spring IoC 容器装配注解：

| Spring 注解     | 场景说明                                    | 起始版本 |
| --------------- | ------------------------------------------- | -------- |
| @ImportResource | 替换 XML 元素<import>                       | 3.0      |
| @Import         | 导入 Configuration Class                    | 3.0      |
| @ComponenetScan | 扫描指定 package 下标注 Spring 模式注解的类 | 3.1      |

相关的示例：

```java
@ImportResource("classpath:/META-INF/dependency-lookup-context.xml")
@Import(User.class)
public class AnnotatedSpringIoCContainerConfigurationDemo {
    public static void main(String[] args) {
        AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext();
        context.register(AnnotatedSpringIoCContainerConfigurationDemo.class);
        context.refresh();
        Map<String, User> userMap = context.getBeansOfType(User.class);
        for (Map.Entry<String, User> entry : userMap.entrySet()) {
            System.out.printf("User Bean name:%s,content: %s \n", entry.getKey(), entry.getValue());
        }
        context.close();
    }
}
```

Spring IoC 配置属性注解：

| Spring 注解      | 场景说明                         | 起始版本 |
| ---------------- | -------------------------------- | -------- |
| @PropertySource  | 配置属性抽象 PropertySource 注解 | 3.1      |
| @PropertySources | @PropertySource 集合注解         | 4.0      |

```java
@PropertySource("classpath:/META-INF/users-config-definitions.properties") //Java8 + @Repeatable
@PropertySource("classpath:/META-INF/users-config-definitions.properties")
//@PropertySources(@PropertySource(value = "1"))
```

## 基于 Extensible XML authoring 扩展 Spring XML 元素

Spring XML 扩展的步骤：

1. 编写 XML Schema 文件：定义 XML 结构
2. 自定义 NamespaceHandler 实现：命名空间绑定
3. 定义 BeanDefinitionParser 实现：XML 元素与 BeanDefinition 解析
4. 注册 XML 扩展：命名空间与 XML Schema 映射

定义 XML 结构：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:users="http://jycoder.org/schema/users"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
       http://jycoder.org/schema/users">

    <users:user id="1" name="jiyongchao" city="SHANGHAI" />

</beans>
```

命名空间绑定：

```java
public class UsersNamespaceHandler extends NamespaceHandlerSupport {

    @Override
    public void init() {
        // 将"user"元素注册对应的BeanDefinitionParser实现
        registerBeanDefinitionParser("user",new UserBeanDefinitionParser());
    }
}
```

XML 元素与 BeanDefinition 解析：

```java
public class UserBeanDefinitionParser extends AbstractSingleBeanDefinitionParser {
    @Override
    protected Class<?> getBeanClass(Element element) {
        return User.class;
    }

    @Override
    protected void doParse(Element element, ParserContext parserContext, BeanDefinitionBuilder builder) {
        setPropertyValue("id", element, builder);
        setPropertyValue("name", element, builder);
        setPropertyValue("City", element, builder);
    }

    private void setPropertyValue(String attributeName, Element element, BeanDefinitionBuilder builder) {
        String attributeValue = element.getAttribute(attributeName);
        if (StringUtils.hasText(attributeValue)) {
            builder.addPropertyValue(attributeName, attributeValue);
        }
    }
}
```

命名空间与 XML Schema 映射：

```properties
#定义namespacehanlder
http\://jycoder.org/schema/users=org.jyc.thinking.in.spring.bean.metadata.UsersNamespaceHandler
```

```properties
http\://jycoder.org/schema/users.xsd=org/jyc/thinking/in/spring/bean/metadata/users.xsd
```

测试我们编写的案例：

```java
public class ExtensibleXmlAuthoringDemo {
    public static void main(String[] args) {
        DefaultListableBeanFactory beanFactory = new DefaultListableBeanFactory();
        XmlBeanDefinitionReader reader = new XmlBeanDefinitionReader(beanFactory);
        reader.loadBeanDefinitions("classpath:/META-INF/users-context.xml");
        // 获取User Bean对象
        User user = beanFactory.getBean(User.class);
        System.out.println(user);
    }
}
```

## 基于 Properties 资源装载外部化配置

1. 注解驱动：
   - org.springframework.context.annotation.PropertySource
   - org.springframework.context.annotation.PropertySources
2. API 编程：
   - org.springframework.core.env.PropertySource
   - org.springframework.core.env.PropertySources

```java
@PropertySource("classpath:/META-INF/users-config-definitions.properties")
public class PropertySourceDemo {
    @Bean
    public User user(@Value("${user.id}") String id, @Value("${user.name}") String name) {
        User user = new User();
        user.setId(id);
        user.setName(name);
        return user;
    }

    public static void main(String[] args) {
        AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext();
        // 扩展Environment中的PropertySources
        // 添加PropertySources操作必须在refresh方法之前完成
        Map<String, Object> propertiesSource = new HashMap<>();
        propertiesSource.put("user.name", "xiao ji");
        org.springframework.core.env.PropertySource propertySource = new MapPropertySource("first-property-source", propertiesSource);
        context.getEnvironment().getPropertySources().addFirst(propertySource);
        context.register(AnnotatedSpringIoCContainerConfigurationDemo.class);
        context.refresh();
        Map<String, User> userMap = context.getBeansOfType(User.class);
        for (Map.Entry<String, User> entry : userMap.entrySet()) {
            System.out.printf("User Bean name:%s,content: %s \n", entry.getKey(), entry.getValue());
        }
        System.out.println(context.getEnvironment().getPropertySources());
        context.close();
    }
}
```

## 基于 yml 资源装载外部化配置

使用 API 编程：

- org.springframework.beans.factory.config.YamlProcessor
  - org.springframework.beans.factory.config.YamlMapFactoryBean
  - org.springframework.beans.factory.config.YamlPropertiesFactoryBean

定义 YAML 文件：

```yaml
user:
  id: 100
  name: 胡先森
```

定义 XML 文件：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
        http://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="yamlMap" class="org.springframework.beans.factory.config.YamlMapFactoryBean">
        <property name="resources" value="classpath:/META-INF/user.yaml" />
    </bean>

</beans>
```

测试我们的例子：

```java
public class XmlBasedYamlPropertySourceDemo {

    public static void main(String[] args) {

        DefaultListableBeanFactory beanFactory = new DefaultListableBeanFactory();
        XmlBeanDefinitionReader reader = new XmlBeanDefinitionReader(beanFactory);
        reader.loadBeanDefinitions("classpath:/META-INF/yaml-property-source-context.xml");
        // 获取User Bean对象
        User user = beanFactory.getBean("user", User.class);
        System.out.println(user);
    }
}
```

PropertySource 默认是没有 yaml 格式的实现的，我们可以自己实现一个：

```java
public class YamlPropertySourceFactory implements PropertySourceFactory {
    @Override
    public PropertySource<?> createPropertySource(String name, EncodedResource resource) throws IOException {
        YamlPropertiesFactoryBean yamlPropertiesFactoryBean = new YamlPropertiesFactoryBean();
        yamlPropertiesFactoryBean.setResources(resource.getResource());
        Properties yamlProperties = yamlPropertiesFactoryBean.getObject();
        return new PropertiesPropertySource(name, yamlProperties);
    }
}
```

然后使用 YAML 的方式装载外部化配置：

```java
@PropertySource(name = "yamlPropertySource",
        value = "classpath:/META-INF/user.yaml",
        factory = YamlPropertySourceFactory.class)
public class AnnotatedYamlPropertySourceDemo {

    @Bean
    public User user(@Value("${user.id}") String id, @Value("${user.name}") String name) {
        User user = new User();
        user.setId(id);
        user.setName(name);
        return user;
    }

    public static void main(String[] args) {
        AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext();
        context.register(AnnotatedYamlPropertySourceDemo.class);
        context.refresh();
        User user = context.getBean("user", User.class);
        System.out.println(user);
        context.close();
    }
}
```

## 面试题

### Spring 内建的 XML Schema 常见有哪些？

见基于 XML 资源装载 Spring 容器配置元信息章节表格。

### Spring 配置元信息有哪些？

- Bean 配置元信息：通过媒介（如 XML、Properties）等，解析 BeanDefinition
- IoC 容器配置元信息：通过媒介（如 XML、Properties 等），控制 IoC 容器行为，比如注解驱动，AOP 等
- 外部化配置：通过资源抽象（如 Properties、YAML 等），控制 PropertySource
- Spring Profile：通过外部化配置，提供条件分支流程

### Extensible XML authoring 的缺点？

- 高复杂度：开发人员需要熟悉 XML schema、Spring.handlers，Spring.schemas 以及 Spring API
- 嵌套元素支持较弱：通常需要使用方法递归或者嵌套解析的方式处理嵌套（子）元素
- XML 处理性能较差：Spring XML 基于 DOM Levels API 实现，该 API 便于理解，然而性能较差
- XML 框架移植性较差：很难适配高性能和便利性的 XML 框架，如 JAXB。

# Spring 资源管理

> 为什么 Spring 不使用 Java 标准资源管理，而选择重新发明轮子？
>
> - Java 标准资源管理强大，然而扩展复杂，资源存储方式并不统一
> - Spring 要自立门户
> - Spring “抄”、“超”、“潮”

## Java 标准资源管理

Java 标准资源定位：

| 职责         | 说明                                                                 |
| ------------ | -------------------------------------------------------------------- |
| 面向资源     | 文件系统、artifact（jar、war、ear 文件）以及远程资源（HTTP、FTP 等） |
| API 整合     | java.lang.ClassLoader#getResource、java.io.File 或 java.net.URL      |
| 资源定位     | java.net.URL 或 java.net.URI                                         |
| 面向流失存储 | java.net.URLConnection                                               |
| 协议扩展     | java.net.URLStreamHandler 或 java.net.URLStreamHandleFactory         |

## Resource 接口

资源接口：

| 类型       | 接口                                                |
| ---------- | --------------------------------------------------- |
| 输入流     | org.springframework.core.io.InputStreamResource     |
| 只读资源   | org.springframework.core.io.Resource                |
| 可写资源   | org.springframework.core.io.WritableResource        |
| 编码资源   | org.springframework.core.io.support.EncodedResource |
| 上下文资源 | org.springframework.core.io.ContextResource         |

## 内建的 Resource 实现

内建实现：

| 资源来源       | 资源协议       | 实现类                                                           |
| -------------- | -------------- | ---------------------------------------------------------------- |
| Bean 定义      | 无             | org.springframework.beans.factory.support.BeanDefinitionResource |
| 数组           | 无             | org.springframework.core.io.ByteArrayResource                    |
| 类路径         | classpath:/    | org.springframework.core.io.ClassPathResource                    |
| 文件系统       | file:/         | org.springframework.core.io.FileSystemResource                   |
| URL            | URL 支持的协议 | org.springframework.core.io.UrlResource                          |
| ServletContext | 无             | org.springframework.web.context.support.ServletContextResource   |

## Resource 接口扩展

1. 可写资源接口
   - org.springframework.core.io.WritableResource
     - org.springframework.core.io.FileSystemResource
     - org.springframework.core.io.FileUrlResource（@since 5.0.2）
     - org.springframework.core.io.PathResource（@since 4.0 & @Deprecated）
2. 编码资源接口
   - org.springframework.core.io.support.EncodedResource

使用编码资源接口进行操作的示例：

```java
public class EncodedFileSystemResourceDemo {
    public static void main(String[] args) throws Exception {
        String currentJavaFilePath = System.getProperty("user.dir") + "/bean-resource/src/main/java/org/jyc/thinking/in/spring/resource/EncodedFileSystemResourceDemo.java";
        File currentJavaFile = new File(currentJavaFilePath);
        FileSystemResource fileSystemResource = new FileSystemResource(currentJavaFile);
        EncodedResource encodedResource = new EncodedResource(fileSystemResource, "UTF-8");
        // 字符输入流
        try (Reader reader = encodedResource.getReader()) {
            System.out.println(IOUtils.toString(reader));
        }
    }
}
```

## Spring 资源加载器

Resource 加载器：

- org.springframework.core.io.ResourceLoader
  - org.springframework.core.io.DefaultResourceLoader
  - org.springframework.core.io.FileSystemResourceLoader
  - org.springframework.core.io.ClassRelativeResourceLoader
  - org.springframework.context.support.AbstractApplicationContext

使用示例：

```java
public class EncodedFileSystemResourceLoaderDemo {
    public static void main(String[] args) throws Exception {
        String currentJavaFilePath = System.getProperty("user.dir") + "/bean-resource/src/main/java/org/jyc/thinking/in/spring/resource/EncodedFileSystemResourceLoaderDemo.java";
        FileSystemResourceLoader resourceLoader = new FileSystemResourceLoader();
        Resource fileSystemResource = resourceLoader.getResource(currentJavaFilePath);
        EncodedResource encodedResource = new EncodedResource(fileSystemResource, "UTF-8");
        // 字符输入流
        try (Reader reader = encodedResource.getReader()) {
            System.out.println(IOUtils.toString(reader));
        }
    }
}
```

## Spring 通配路径资源加载器

1. 通配路径 ResourceLoader
   - org.springframework.core.io.support.ResourcePatternResolver
   - org.springframework.core.io.support.PathMatchingResourcePatternResolver
2. 路径匹配器
   - org.springframework.util.PathMatcher
     - Ant 模式匹配实现 - org.springframework.util.AntPathMatcher

## Spring 通配路径资源扩展

1. 实现 org.springframework.util.PathMatcher
2. 重置 PathMatcher
   - PathMatchingResourcePatternResolver#setPathMatcher

相关的示例：

```java
public class CustomizedResourcePatternResolver {
    public static void main(String[] args) throws Exception {
        // 读取当前package对应的所有的.java文件
        // *.java
        String currentPackagePath = System.getProperty("user.dir") + "/bean-resource/src/main/java/org/jyc/thinking/in/spring/resource/";
        String locationPattern = currentPackagePath + "*.java";
        PathMatchingResourcePatternResolver resourcePatternResolver = new PathMatchingResourcePatternResolver(new FileSystemResourceLoader());

        resourcePatternResolver.setPathMatcher(new JavaFilePathMatcher());
        Resource[] resources = resourcePatternResolver.getResources(locationPattern);
        Stream.of(resources).map(ResourceUtils::getContent).forEach(System.out::println);
    }

    static class JavaFilePathMatcher implements PathMatcher {
        @Override
        public boolean isPattern(String path) {
            return path.endsWith(".java");
        }

        @Override
        public boolean match(String pattern, String path) {
            return path.endsWith(".java");
        }

        @Override
        public boolean matchStart(String pattern, String path) {
            return false;
        }

        @Override
        public String extractPathWithinPattern(String pattern, String path) {
            return null;
        }

        @Override
        public Map<String, String> extractUriTemplateVariables(String pattern, String path) {
            return null;
        }

        @Override
        public Comparator<String> getPatternComparator(String path) {
            return null;
        }

        @Override
        public String combine(String pattern1, String pattern2) {
            return null;
        }
    }
}
```

其中使用到的工具类：

```java
public interface ResourceUtils {

    static String getContent(Resource resource) {
        try {
            return getContent(resource, "UTF-8");
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
    }

    static String getContent(Resource resource, String encoding) throws IOException {
        EncodedResource encodedResource = new EncodedResource(resource, encoding);
        try (Reader reader = encodedResource.getReader()) {
            return IOUtils.toString(reader);
        }
    }
}
```

## 依赖注入 Spring Resource

可以基于@Value 实现：

```java
@Value("classpath:/...")
private Resource resource;
```

相关的示例：

```java
public class InjectResourceDemo {

    @Value("classpath:/META-INF/default.properties")
    private Resource defaultPropertiesResource;

    @Value("classpath*:/META-INF/*.properties")
    private Resource[] PropertiesResources;

    @Value("${user.dir}")
    private String currentProjectRootPath;

    @PostConstruct
    public void init() {
        System.out.println(ResourceUtils.getContent(defaultPropertiesResource));
        System.out.println(currentProjectRootPath);
        Stream.of(PropertiesResources).map(ResourceUtils::getContent).forEach(System.out::println);
    }

    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(InjectResourceDemo.class);
        applicationContext.refresh();
        // 关闭应用上下文
        applicationContext.close();
    }
}
```

## 依赖注入 ResourceLoader

有多种方式可以依赖注入 ResourceLoader：

1. 实现 ResourceLoaderAware 回调
2. @Autowired 注入 ResourceLoader
3. 注入 ApplicationContext 作为 ResourceLoader

```java
public class InjectResourceLoaderDemo implements ResourceLoaderAware {

    private ResourceLoader awareResourceLoader;

    @Autowired
    ResourceLoader autowiredResourceLoader;

    @Autowired
    private AbstractApplicationContext applicationContext;

    @PostConstruct
    public void init() {
        System.out.println("awareResourceLoader == autowiredResourceLoader: " + (autowiredResourceLoader == awareResourceLoader));
        System.out.println("autowiredResourceLoader == applicationContext: " + (awareResourceLoader == applicationContext));
    }

    public static void main(String[] args) {
        AnnotationConfigApplicationContext applicationContext = new AnnotationConfigApplicationContext();
        applicationContext.register(InjectResourceLoaderDemo.class);
        applicationContext.refresh();
        // 关闭应用上下文
        applicationContext.close();
    }

    @Override
    public void setResourceLoader(ResourceLoader resourceLoader) {
        this.awareResourceLoader = resourceLoader;
    }
}
```

> 这三种不同的方式最终注入的是相同的对象，都是 AbstractApplicationContext。

## 面试题

### Spring 配置资源中有哪些常见类型？

XML 资源、Properties 资源、YAML 资源。

### 请举例不同类型的 Spring 配置资源

XML 资源：

1. 普通的 BeanDefinition XML 资源配置 - \*.xml
2. Spring Schema 资源 - \*.xsd

Properties 资源：

1. 普通 Properties 格式资源 - \*.properties
2. Spring Handler 实现类映射文件 - META/spring.handlers
3. Spring Schema 资源映射文件 - META-INF/spring.schemas

YAML 资源：

1. 普通 YAML 资源配置 - _.yaml 或 _.yml

### Java 标准资源管理扩展的步骤

简易实现：

- 实现 URLStreamHandler 并放置再 sun.net.www.protocol.${protocol}.Handler包下

自定义实现：

- 实现 URLStreamHandler
- 添加 -Djava.protocol.handler.pkgs 启动参数，指向 URLStreamHandler 实现类的包下

高级实现：

- 实现 URLStreamHandlerFactory 并传递到 URL 之中

# Spring 国际化

Spring 国际化使用场景：

- 普通国际化文案
- Bean Validation 校验国际化文案
- Web 站点页面渲染
- Web MVC 错误消息提示

## Spring 国际化接口

核心接口：

- org.springframework.context.MessageSource

主要概念：

- 文案模板编码（code）
- 文案模板参数（args）
- 区域（Locale）

## 层次性的 MessageSource

Spring 层次性国际化接口：

- org.springframework.context.HierarchicalMessageSource

## Java 国际化标准实现

核心接口：

- 抽象实现 - java.util.ResourceBundle
- Properties 资源实现 - java.util.PropertyResourceBundle
- 列举实现 - java.util.ListResourceBundle

ResourceBundle 核心特性：

- Key - Value 设计
- 层次性设计
- 缓存设计
- 字符编码控制 - java.util.ResourceBundle.Control（@since 1.6）
- Control SPI 扩展 - java.util.spi.ResourceBundleControlProvider（@since 1.8）

## Java 文本格式化

核心接口：

- java.text.MessageFormat

基本用法：

- 设置消息格式模式 - new MessageFormat(...)
- 格式化 - format(new Objectp[]{...})

消息格式模式：

- 格式元素：{ArgumentIndex（,FormatType,（FormatStyle））}
- FormatType：消息格式类型，可选项，每种类型在 number、date、time 和 choice 类型选其一
- FormatStyle：消息格式风格，可选项，包括：short、medium、long、full、integer、currency、percent

```java
public class MessageFormatDemo {
    public static void main(String[] args) {
        int planet = 7;
        String event = "a disturbance in the Force";

        String result = MessageFormat.format(
                "At {1,time,long} on {1,date}, there was {2} on planet {0,number,integer}.",
                planet, new Date(), event);
        System.out.println(result);
    }
}
```

Java 文本格式化还有一些高级特性：

- 重置消息格式模板
- 重置 java.util.Locale
- 重置 java.text.Format

使用的示例：

```java
public class MessageFormatDemo {
    public static void main(String[] args) {
        int planet = 7;
        String event = "a disturbance in the Force";

        String messageFormatPattern = "At {1,time,long} on {1,date}, there was {2} on planet {0,number,integer}.";
        MessageFormat messageFormat = new MessageFormat(messageFormatPattern);
        String result = messageFormat.format(new Object[]{planet, new Date(), event});
        System.out.println(result);

        // 重置MessageFormatPattern
        messageFormatPattern = "This is a text: {0},{1},{2}";
        messageFormat.applyPattern(messageFormatPattern);
        result = messageFormat.format(new Object[]{"hello,world", "666"});
        System.out.println(result);

        // 重置Locale
        messageFormat.setLocale(Locale.ENGLISH);
        messageFormatPattern = "At {1,time,long} on {1,date}, there was {2} on planet {0,number,integer}.";
        messageFormat.applyPattern(messageFormatPattern);
        result = messageFormat.format(new Object[]{planet, new Date(), event});
        System.out.println(result);

        // 重置Format
        // 根据参数索引来设置 Pattern
        messageFormat.setFormat(1, new SimpleDateFormat("YYYY-MM-dd HH:mm:ss"));
        result = messageFormat.format(new Object[]{planet, new Date(), event});
        System.out.println(result);
    }
}
```

## MessageSource 开箱实现

基于 ResourceBundle + MessageFormat 组合 MessageSource 实现：

- org.springframework.context.support.ResourceBundleMessageSource

可重载 Properties + MessageFormat 组合 MessageSource 实现：

- org.springframework.context.support.ReloadableResourceBundleMessageSource

## Message 的内建依赖

MessageSource 内建 Bean 可能来源：

- 预注册 Bean 名称为："messageSource"，类型为：MessageSource Bean
- 默认内建实现 - DelegatingMessageSource
  - 层次性查找 MessageSource 对象

相关的代码实现：

```java
protected void initMessageSource() {
		ConfigurableListableBeanFactory beanFactory = getBeanFactory();
		if (beanFactory.containsLocalBean(MESSAGE_SOURCE_BEAN_NAME)) {
			this.messageSource = beanFactory.getBean(MESSAGE_SOURCE_BEAN_NAME, MessageSource.class);
			// Make MessageSource aware of parent MessageSource.
			if (this.parent != null && this.messageSource instanceof HierarchicalMessageSource) {
				HierarchicalMessageSource hms = (HierarchicalMessageSource) this.messageSource;
				if (hms.getParentMessageSource() == null) {
					// Only set parent context as parent MessageSource if no parent MessageSource
					// registered already.
					hms.setParentMessageSource(getInternalParentMessageSource());
				}
			}
			if (logger.isTraceEnabled()) {
				logger.trace("Using MessageSource [" + this.messageSource + "]");
			}
		}
		else {
			// Use empty MessageSource to be able to accept getMessage calls.
			DelegatingMessageSource dms = new DelegatingMessageSource();
			dms.setParentMessageSource(getInternalParentMessageSource());
			this.messageSource = dms;
			beanFactory.registerSingleton(MESSAGE_SOURCE_BEAN_NAME, this.messageSource);
			if (logger.isTraceEnabled()) {
				logger.trace("No '" + MESSAGE_SOURCE_BEAN_NAME + "' bean, using [" + this.messageSource + "]");
			}
		}
	}
```

## SpringBoot 为什么要新建 MessageSource Bean?

1. AbstractApplicationContext 的实现决定了 MessageSource 内建实现
2. Spring Boot 通过外部化配置简化了 MessageSource Bean 构建
3. SPring Boot 基于 Bean Validation 校验非常普遍

实际上我们可以覆盖 SpringBoot 中自动装配的 MessageSource Bean：

```java
@EnableAutoConfiguration
public class CustomizedMessageSourceBeanDemo {

    /**
     * 在Spring Boot场景中，Primary Configure Sources（Classes）高于*AutoConfiguration
     *
     * @return
     */
    @Bean
    public MessageSource messageSource() {
        return new ReloadableResourceBundleMessageSource();
    }

    public static void main(String[] args) {
        ConfigurableApplicationContext applicationContext = SpringApplication.run(CustomizedMessageSourceBeanDemo.class, args);
        ConfigurableListableBeanFactory beanFactory = applicationContext.getBeanFactory();
        if (beanFactory.containsBean(AbstractApplicationContext.MESSAGE_SOURCE_BEAN_NAME)) {
            beanFactory.getBean(AbstractApplicationContext.MESSAGE_SOURCE_BEAN_NAME);
            // 查找MessageSource Bean
            MessageSource messageSource = applicationContext.getBean(AbstractApplicationContext.MESSAGE_SOURCE_BEAN_NAME, MessageSource.class);
            System.out.println(messageSource);
        }
    }
}
```

## 面试题

### Spring 国际化接口有哪些？

1. 核心接口 - MessageSource
2. 层次性接口 - org.springframework.context.HierarchicalMessageSource

### Spring 有哪些 MessageSource 的内建实现？

- org.springframework.context.support.ResourceBundleMessageSource
- org.springframework.context.support.ReloadableResourceBundleMessageSource
- org.springframework.context.support.StaticMessageSource
- org.springframework.context.support.DelegatingMessageSource

### 如何实现配置自动更新 MessageSource？

主要技术：

- Java NIO 2：java.nio.file.watchService
- Java Concurrency：java.util.concurrent.ExecutorService
- Spring：org.springframework.context.support.AbstractMessageSource

# Spring 校验

Spring 校验使用场景：

- Spring 常规校验（Validator）
- Spring 数据绑定（DataBinder）
- Spring Web 参数绑定（WebDataBinder）
- Spring WebMVC/WebFlux 处理方法参数校验

## Validator 接口设计

接口职责：

- Spring 内部校验接口，通过编程的方式校验目标对象

核心方法：

- supports（Class）：校验目标类能否校验
- validate（Object，Errors）：校验目标对象，并将校验失败的内容输出至 Errors 对象

配套组件：

- 错误收集器：org.springframework.validation.Errors
- Validator 工具类：org.springframework.validation.ValidationUtils

在 Java Doc 中的例子：

```java
public class UserLoginValidator implements Validator {

      private static final int MINIMUM_PASSWORD_LENGTH = 6;

      public boolean supports(Class clazz) {
         return UserLogin.class.isAssignableFrom(clazz);
      }

      public void validate(Object target, Errors errors) {
         ValidationUtils.rejectIfEmptyOrWhitespace(errors, "userName", "field.required");
         ValidationUtils.rejectIfEmptyOrWhitespace(errors, "password", "field.required");
         UserLogin login = (UserLogin) target;
         if (login.getPassword() != null
               && login.getPassword().trim().length() < MINIMUM_PASSWORD_LENGTH) {
            errors.rejectValue("password", "field.min.length",
                  new Object[]{Integer.valueOf(MINIMUM_PASSWORD_LENGTH)},
                  "The password must be at least [" + MINIMUM_PASSWORD_LENGTH + "] characters in length.");
         }
      }
   }
```

## Errors 接口设计

接口职责：

- 数据绑定和校验错误收集接口，与 Java Bean 和其属性有强关联性。

核心方法：

- reject 方法（重载）：收集错误文案
- rejectValue 方法（重载）：收集对象字段中的错误文案

配套组件：

- Java Bean 错误描述：org.springframework.validation.ObjectError
- Java Bean 属性错误描述：org.springframework.validation.FieldError

## Errors 的文案来源

Errors 文案生成步骤：

1. 选择 Errors 实现（org.springframework.validation.BeanPropertyBindingResult）
2. 调用 reject 方法或 rejectValue 方法
3. 获取 Errors 对象中 ObjectError 或 FieldError
4. 将 ObjectError 或 FieldError 中的 code 和 args，关联 MessageSource 实现（如：ResourceBundleMessageSource）

使用的示例：

```java
public class ErrorMessageDemo {
    public static void main(String[] args) {
        // 1.创建User对象
        User user = new User();
        // 2.选择Errors - BeanPropertyBindingResult
        Errors errors = new BeanPropertyBindingResult(user, "user");
        // 3.调用reject或者rejectValue
        // reject生成ObjectError
        // reject生成 FildError
        errors.reject("user.properties.not.null");
        errors.rejectValue("name", "name.required");
        //4.FieldError is ObjectError
        List<ObjectError> globalErrors = errors.getGlobalErrors();
        FieldError fieldError = errors.getFieldError();
        List<ObjectError> allErrors = errors.getAllErrors();
        // 5.通过ObjectError和FieldError中的code和args关联MessageSource实现
        MessageSource messageSource = createMessageSource();

        for (ObjectError error : allErrors) {
            messageSource.getMessage(error.getCode(), error.getArguments(), Locale.getDefault());
            System.out.println(messageSource);
        }
    }

    private static MessageSource createMessageSource() {
        StaticMessageSource staticMessageSource = new StaticMessageSource();
        staticMessageSource.addMessage("user.properties.not.null", Locale.getDefault(), "User 属性不能为空");
        staticMessageSource.addMessage("name.required", Locale.getDefault(), "name is not null");
        return staticMessageSource;
    }
}
```

## 自定义 Validator

实现 org.springframework.validation.Validator 接口，具体操作如下：

- 实现 supports 方法
- 实现 validate 方法
  - 通过 Errors 对象收集错误
    - ObjectError：对象（Bean）错误：
    - FieldError：对象（Bean）属性（Property）错误
  - 通过 ObjectError 和 FieldError 关联 MessageSource 实现获取最终文案

自定义 Validator 的示例：

```java
public class ValidatorDemo {

    public static void main(String[] args) {
        // 1.创建Validator
        Validator validator = new UserValodator();
        // 2.判断是否支持目标对象的类型
        User user = new User();
        System.out.println(validator.supports(user.getClass()));
        // 3.创建Errors对象
        Errors errors = new BeanPropertyBindingResult(user, "user");
        validator.validate(user, errors);
        // 4.获取MessageSource对象
        MessageSource messageSource = createMessageSource();
        // 5.输出所有的错误文案
        for (ObjectError error : errors.getAllErrors()) {
            String message = messageSource.getMessage(error.getCode(), error.getArguments(), Locale.getDefault());
            System.out.println(message);
        }
    }

    static class UserValodator implements Validator {
        @Override
        public boolean supports(Class<?> clazz) {
            return User.class.equals(clazz);
        }

        @Override
        public void validate(Object target, Errors errors) {
            User user = (User) target;
            ValidationUtils.rejectIfEmptyOrWhitespace(errors, "id", "id.required");
            ValidationUtils.rejectIfEmptyOrWhitespace(errors, "name", "name.required");
            String name = user.getName();
            // ...
        }
    }
}
```

## Bean Validation

Bean Validation 与 Validator 适配：

- 核心组件 - org.springframework.validation.beanvalidation.LocalValidatorFactoryBean
- 依赖 Bean Validation - JSR - 303 or JSR - 349 provider
- Bean 方法参数校验 - org.springframework.validation.beanvalidation.MethodValidationPostProcessor

使用示例：

```java
public class SpringBeanValidationDemo {
    public static void main(String[] args) {
        ConfigurableApplicationContext applicationContext = new ClassPathXmlApplicationContext("classpath:/META-INF/bean-validation-context.xml");

//        Validator validator = applicationContext.getBean(Validator.class);
//        System.out.println(validator instanceof LocalValidatorFactoryBean);
        UserProcessor userProcessor = applicationContext.getBean(UserProcessor.class);
        userProcessor.processUser(new User());
        applicationContext.close();
    }

    @Component
    @Validated
    static class UserProcessor {
        public void processUser(@Valid User user) {
            System.out.println(user);
        }
    }

    @Validated
    static class User {

        public String getName() {
            return name;
        }

        @Override
        public String toString() {
            return "User{" +
                    "name='" + name + '\'' +
                    '}';
        }

        public void setName(String name) {
            this.name = name;
        }

        @NotNull
        private String name;
    }
}
```

其中的 XML 文件：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
       http://www.springframework.org/schema/beans/spring-beans.xsd http://www.springframework.org/schema/context https://www.springframework.org/schema/context/spring-context.xsd">

    <context:component-scan base-package="org.jyc.thinking.in.spring.validation" />

    <bean id = "validator" class="org.springframework.validation.beanvalidation.LocalValidatorFactoryBean" />

    <bean class="org.springframework.validation.beanvalidation.MethodValidationPostProcessor">
        <property name="validator" ref="validator" />
    </bean>
</beans>
```

可以看到使用这种方式方便了很多，并且可以根据实际的需求对其进行扩展。

## 面试题

### Spring 校验接口是哪个？

org.springframework.validation.Validator

### Spring 有哪些校验核心组件？

- 校验器：org.springframework.validation.Validator
- 错误收集器：org.springframework.validation.Errors
- Java Bean 错误描述：org.springframework.validation.ObjectError
- Java Bean 属性错误描述：org.springframework.validation.FieldError
- Bean Validation 适配：org.springframework.validation.beanvalidation.LocalValidatorFactoryBean

### 请通过示例演示 Spring Bean 的校验？

// 待续...

# Spring 数据绑定

Spring 数据绑定的使用场景：

1. Spring BeanDefinition 到 Bean 实例创建
2. Spring 数据绑定（DataBinder）
3. Spring Web 参数绑定（WebDataBinder）

## Spring 数据绑定组件

1. 标准组件：
   - org.springframework.validation.DataBinder
2. Web 组件：
   - org.springframework.web.bind.WebDataBinder
   - org.springframework.web.bind.ServletRequestDataBinder
   - org.springframework.web.bind.support.WebRequestDataBinder
   - org.springframework.web.bind.support.WebExchangeDataBinder

DataBinder 的核心属性：

| 属性                 | 说明                           |
| -------------------- | ------------------------------ |
| target               | 关联目标 Bean                  |
| objectName           | 目标 Bean 名称                 |
| bindingResult        | 属性绑定结果                   |
| typeConverter        | 类型转化器                     |
| conversionService    | 类型转化服务                   |
| messageCodesResolver | 校验错误文案 Code 处理器       |
| validators           | 关联的 Bean Validator 实例集合 |

DataBinder 绑定方法 bind（PropertyValues），会将 PropertyValues key-Value 内容映射到关联 Bean（target）中的属性上。

## DataBinder 元数据

DataBinder 元数据 - PropertyValues：

| 特征         | 说明                                                                 |
| ------------ | -------------------------------------------------------------------- |
| 数据来源     | BeanDefinition，主要来源 XML 资源配置 BeanDefinition                 |
| 数据结构     | 由一个或多个 PropertyValue 组成                                      |
| 成员结构     | PropertyValue 包含属性名称，以及属性值（包括原始值、类型转换后的值） |
| 常见实现     | MutablePropertyValue                                                 |
| Web 扩展实现 | ServletConfigPropertyValue，ServletRequestParameterPropertyValues    |
| 相关生命周期 | InstantiationAwareBeanPostProcessor#postProcessProperties            |

## DataBinder 绑定控制参数

DataBinder 绑定特殊场景分析：

- 当 PropertyValues 中包含名称的 x 的 PropertyValue，目标对象 B 不存在 x 属性，当 bind 方法执行时，会发生什么？
- 当 PropertyValues 中包含名称的 x 的 PropertyValue，目标对象 B 中存在 x 属性，当 bind 方法执行时，如何避免 B 属性 x 不被绑定？
- 当 PropertyValues 中包含 x.y 的 PropertyValue，目标对象 B 中存在 x 属性（嵌套 y 属性），当 bind 方法执行时，会发生什么？

相关的示例代码：

```java
	public class DataBinderDemo {
    public static void main(String[] args) {
        // 创建空白对象
        User user = new User();
        // 1.创建DataBinder
        DataBinder dataBinder = new DataBinder(user, "user");

        // 2.创建PropertyValues
        HashMap<String, Object> source = new HashMap<>();
        source.put("id","1");
        source.put("name","胡先森");

        // a.PropertyValues存在user中不存在的属性值
        // DataBinder特性一：忽略了未知的属性
        source.put("age",18);

        // b.PropertyValues存在一个嵌套属性，company.name
        // DataBinder特性二：支持嵌套属性
        source.put("company.name","jjjj");

        MutablePropertyValues propertyValues = new MutablePropertyValues(source);

        dataBinder.bind(propertyValues);

        // 3.输出user
        System.out.println(user);
    }
}
```

DataBinder 绑定控制参数：

| 参数名称            | 说明                               |
| ------------------- | ---------------------------------- |
| ignoreUnknownFields | 是否忽略未知字段，默认值：true     |
| ignoreInvalidFields | 是否忽略非法字段，默认值：false    |
| autoGrowNestedPaths | 是否自动增加嵌套路径，默认值：true |
| allowedFields       | 绑定字段白名单                     |
| disallowedFields    | 绑定字段黑名单                     |
| requiredFields      | 必须绑定字段                       |

相关的示例：

```java
public class DataBinderDemo {
    public static void main(String[] args) {
        // 创建空白对象
        User user = new User();
        // 1.创建DataBinder
        DataBinder dataBinder = new DataBinder(user, "user");

        // 2.创建PropertyValues
        HashMap<String, Object> source = new HashMap<>();
        source.put("id", "1");
        source.put("name", "胡先森");

        // a.PropertyValues存在user中不存在的属性值
        // DataBinder特性一：忽略了未知的属性
        source.put("age", 18);

        // b.PropertyValues存在一个嵌套属性，company.name
        // DataBinder特性二：支持嵌套属性
        source.put("company.name", "jjjj");

//        source.put("company", new Company());
//        source.put("company.name","jjjj");

        MutablePropertyValues propertyValues = new MutablePropertyValues(source);

        // 1.调整ignoreUnknownFields true（默认） -> false
//        dataBinder.setIgnoreUnknownFields(false);

        // 2.调整自动增加嵌套路径true（默认） -> false
        dataBinder.setAutoGrowNestedPaths(false);

        // 3.调整ignoreInvalidFields false（默认） -> true
        dataBinder.setIgnoreInvalidFields(true);

        // 4.白名单
        dataBinder.setRequiredFields("id", "name", "city");

        dataBinder.bind(propertyValues);
        // 输出user
        System.out.println(user);

        // 5.获取绑定结果（结果包含错误文案code，不会抛出异常）
        BindingResult result = dataBinder.getBindingResult();
        System.out.println(result);
    }
}
```

## Spring 底层 Java Beans 替换实现

1. Java Beans 核心实现 - java.beans.BeanInfo
   - 属性（Property）
     - java.beans.PropertyEditor
   - 方法（Method）
   - 事件（Event）
   - 表达式（Expression）
2. Spring 替代实现 - org.springframework.beans.BeanWrapper
   - 属性（Property）
     - java.beans.PropertyEditor
   - 嵌套属性路径（nested path）

## BeanWrapper 使用场景

- Spring 底层 JavaBeans 基础设施的中心化接口
- 通常不会直接使用，间接用于 BeanFactory 和 DataBinder
- 提供标准 JavaBeans 分析和操作，能够单独或批量存储 Java Bean 的属性（properties）
- 支持嵌套属性路径（nested path）
- 实现类 org.springframework.beans.BeanWrapperImpl

## JavaBeans 操作属性

标准的 JavaBeans 是如何操作属性的？

| API                           | 说明                     |
| ----------------------------- | ------------------------ |
| java.beans.Introspector       | JavaBeans 内省 API       |
| java.beans.BeanInfo           | Java Bean 元信息 API     |
| java.beans.BeanDescriptor     | Java Bean 信息描述符     |
| java.beans.PropertyDescriptor | Java Bean 属性描述符     |
| java.beans.MethodDescriptor   | Java Bean 方法描述符     |
| java.beans.EventSetDescriptor | Java Bean 事件集合描述符 |

> PropertyDescriptor 并不要求 setter、getter 方法均存在。

可以使用如下示例进行观察：

```java
public class JavaBeansDemo {
    public static void main(String[] args) throws Exception {
        // stopClass排除（截止）类
        BeanInfo beanInfo = Introspector.getBeanInfo(User.class, Object.class);

        // 属性描述符 PropertyDescriptor
        // 所有的Java类均继承 java.lang.Object方法
        // Class属性来自于Object#getClass() 方法
        Stream.of(beanInfo.getPropertyDescriptors()).forEach(propertyDescriptor -> {
            propertyDescriptor.getReadMethod(); // Getter方法
            propertyDescriptor.getWriteMethod(); // Setter方法
            System.out.println(propertyDescriptor);
        });
        // 输出User定义的方法 MethodDescriptor
        Stream.of(beanInfo.getMethodDescriptors()).forEach(System.out::println);
    }
}
```

## DataBinder 数据校验

DataBinder 与 BeanWrapper 的联系：

- bind 方法生成 BeanPropertyBindingResult
- BeanPropertyBindingResult 关联 BeanWrapper

## 面试题

### Spring 数据绑定 API 是什么？

org.springframework.validation.DataBinder

### BeanWrapper 与 JavaBeans 之间的关系是？

BeanWrapper 是 Spring 底层 JavaBeans 基础设施的中心化接口。

### DataBinder 是怎么完成属性类型转换的？

// ...

# Spring 类型转换

Spring 类型转换的实现方案：

1. 基于 JavaBeans 接口的类型转换实现
   - 基于 java.beans.PropertyEditor 扩展
2. Spring 3.0+ 通用类型转换实现

## 使用场景

场景分析：

| 场景               | 基于 JavaBeans 接口的类型转换实现 | Spring 3.0+通用类型转换实现 |
| ------------------ | --------------------------------- | --------------------------- |
| 数据绑定           | YES                               | YES                         |
| BeanWrapper        | YES                               | YES                         |
| Bean 属性类型转换  | YES                               | YES                         |
| 外部化属性类型转换 | NO                                | YES                         |

## 基于 JavaBeans 接口的类型转换

1. 核心职责：
   - 将 String 类型转化为目标类型的对象
2. 扩展原理：
   - Spring 框架将文本内容传递到 PropertyEditor 实现的 setAsText(String)方法
   - PropertyEditor#setAsText(String)方法实现将 String 类型转化为目标类型的对象
   - 将目标类型的对象传入 PropertyEditor#setAsValue(Object)方法
   - PropertyEditor#setAsValue(Object)方法实现需要临时存储传入对象
   - Spring 框架将通过 PropertyEditor#getValue()获取类型转换后的对象

我们可以模拟一下整个过程：

```java
public class StringToPropertiesPropertyEditor extends PropertyEditorSupport implements PropertyEditor {

    // 1.实现setAsText方法
    @Override
    public void setAsText(String text) throws IllegalArgumentException {
        // 2.将String类型转换成Properties类型
        Properties properties = new Properties();
        try {
            properties.load(new StringReader(text));
        } catch (IOException e) {
            e.printStackTrace();
        }
        // 3.临时存储Properties对象
        setValue(properties);
        // next 获取临时Properties对象 # getValue
    }
}
```

然后观察输出：

```java
public class PropertyEditorDemo {
    public static void main(String[] args) {
        // 模拟Spring Framework的操作
        // 有一段文本name = "胡先森";
        String text = "name = 胡先森";
        PropertyEditor propertyEditor = new StringToPropertiesPropertyEditor();
        propertyEditor.setAsText(text);
        System.out.println(propertyEditor.getValue());
    }
}
```

## Spring 内建 PropertyEditor 扩展

内建扩展（org.springframework.beans.propertyeditors）：

| 转换场景            | 实现类                                                            |
| ------------------- | ----------------------------------------------------------------- |
| String -> Byte 数组 | org.springframework.beans.propertyeditors.ByteArrayPropertyEditor |
| String -> Char      | org.springframework.beans.propertyeditors.CharacterEditor         |
| String -> Char 数组 | org.springframework.beans.propertyeditors.CharArrayPropertyEditor |
| String -> Charset   | org.springframework.beans.propertyeditors.CharsetEditor           |
| String -> Class     | org.springframework.beans.propertyeditors.ClassEditor             |
| String -> Currency  | org.springframework.beans.propertyeditors.CurrencyEditor          |
| ...                 | ...                                                               |

## 自定义 PropertyEditor 扩展

实现步骤如下：

1. 扩展模式：
   - 扩展 java.beans.PropertyEditorSupport 类
2. 实现 org.springframework.beans.PropertyEditorRegistrar
   - 实现 registerCustomEditor（org.springframework.beans.PropertyEditorRegistry）方法
   - 将 PropertyEditorRegistry 实现注册为 Spring Bean
3. 向 org.springframework.beans.PropertyEditorRegistry 注册自定义 PropertyEditor 实现
   - 通用类型实现：registerCustomEditor(Class<?> requiredType, PropertyEditor propertyEditor);
   - Java Bean 属性类型实现：registerCustomEditor(Class<?> requiredType, String propertyPath, PropertyEditor propertyEditor);

相关的示例，第一步：

```java
public class StringToPropertiesPropertyEditor extends PropertyEditorSupport implements PropertyEditor {

    // 1.实现setAsText方法
    @Override
    public void setAsText(String text) throws IllegalArgumentException {
        // 2.将String类型转换成Properties类型
        Properties properties = new Properties();
        try {
            properties.load(new StringReader(text));
        } catch (IOException e) {
            e.printStackTrace();
        }
        // 3.临时存储Properties对象
        setValue(properties);
        // next 获取临时Properties对象 # getValue
    }

    @Override
    public String getAsText() {
        Properties properties = (Properties) getValue();
        StringBuilder textBuilder = new StringBuilder();
        for (Map.Entry<Object, Object> entry : properties.entrySet()) {
            textBuilder.append(entry.getKey()).append("=").append(entry.getValue()).append(System.getProperty("line.separator"));
        }
        return textBuilder.toString();
    }
}
```

第二步和第三步：

```java
// @Component // 3.将其声明为Spring Bean
public class CustomizedPropertyEditorRegistrar implements PropertyEditorRegistrar {
    @Override
    public void registerCustomEditors(PropertyEditorRegistry registry) {
        // 1.通用类型转换
        // 2.Java Bean属性类型转换
        registry.registerCustomEditor(User.class, "context", new StringToPropertiesPropertyEditor());

    }
}
```

这里我们不采用注解的方式，而是采用 XML 的方式进行配置，将 CustomizedPropertyEditorRegistrar 声明为 Spring Bean：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
       http://www.springframework.org/schema/beans/spring-beans.xsd">
    <bean id="user" class="org.jyc.thinking.in.spring.ioc.overview.dependency.domain.User">
        <property name="id" value="1"/>
        <property name="name" value="胡先森"/>
        <property name="context"> <!-- Properties类型 -->
            <value>
                id = 1
                name = 胡先森
            </value>
        </property>
    </bean>

    <bean class="org.jyc.thinking.in.spring.conversion.CustomizedPropertyEditorRegistrar"/>
</beans>
```

测试类：

```java
public class SpringCustomizedPropertyEditorDemo {
    public static void main(String[] args) {
        ConfigurableApplicationContext applicationContext = new ClassPathXmlApplicationContext("classpath:/META-INF/property-editors-context.xml");
        User user = applicationContext.getBean("user", User.class);
        System.out.println(user);
        // 关闭应用上下文
        applicationContext.close();
    }
}
```

## PropertyEditor 的局限性

- 违反单一原则
  - java.beans.PropertyEditor 接口职责太多，除了类型转换，还包括 Java Beans 事件和 Java GUI 交互
- java.beans.PropertyEditor 实现类型局限
  - 来源类型只能为 java.lang.String 类型
- java.beans.PropertyEditor 实现缺少类型安全
  - 除了实现类名可以表达语义，实现类无法感知目标转换类型

## Spring3 通用类型转换接口

1. 类型转换接口 - org.springframework.core.convert.converter.Converter<S, T>
   - 泛型参数 S：来源类型，参数 T：目标类型
   - 核心方法：T convert(S)
2. 通用类型转换接口 - org.springframework.core.convert.converter.GenericConverter
   - 核心方法：convert(Object source, TypeDescriptor sourceType, TypeDescriptor targetType);
   - 配对类型：org.springframework.core.convert.converter.GenericConverter.ConvertiblePair
   - 类型描述：org.springframework.core.convert.TypeDescriptor

## Spring 内建类型转换器

| 转换场景             | 实现类所在包名(package)                      |
| -------------------- | -------------------------------------------- |
| 日期/时间相关        | org.springframework.format.datetime          |
| Java 8 日期/时间相关 | org.springframework.format.datetime.standard |
| 通用实现             | org.springframework.core.convert.support     |

## Converter 接口的局限性

- 局限一：缺少 Source Type 和 Target Type 前置判断
  - 应对：增加 org.springframework.core.convert.converter.ConditionalConverter 实现
- 局限二：仅能转换单一的 Source Type 和 Target Type
  - 应对：使用 org.springframework.core.convert.converter.GenericConverter 代替

## GenericConverter 接口

org.springframework.core.convert.converter.GenericConverter 的介绍：

| 核心要素 | 说明                                                                         |
| -------- | ---------------------------------------------------------------------------- |
| 使用场景 | 用于"复合"类型转换场景，比如 Collection、Map、数组等                         |
| 转换范围 | Set<ConvertiblePair> getConvertibleTypes()                                   |
| 配对类型 | org.springframework.core.convert.converter.GenericConverter.ConvertiblePair  |
| 转换方法 | convert(Object source, TypeDescriptor sourceType, TypeDescriptor targetType) |
| 类型描述 | org.springframework.core.convert.TypeDescriptor                              |

> "复合"类型在进行转换的时候，可以利用 Converter 接口，对集合（或其他类型）中的元素进行转换。

## 优化 GenericConverter 接口

GenericConverter 局限性：

- 缺少 Source TYpe 和 Target Type 前置判断
- 单一类型转换实现复杂

GenericConverter 优化接口 - ConditionalGenericConverter

- 复合类型转换 ：org.springframework.core.convert.converter.GenericConverter
- 类型条件判断：org.springframework.core.convert.converter.ConditionalConverter

## 扩展 Spring 类型转换器

扩展的步骤：

1. 实现转换器接口
   - org.springframework.core.convert.converter.Converter
   - org.springframework.core.convert.converter.ConverterFatory
   - org.springframework.core.convert.converter.GenericConverter
2. 注册转换器实现
   - 通过 ConversionServiceFactoryBean（Spring Bean）
   - 通过 org.springframework.core.convert.ConversionService（API）

相关的示例如下，步骤一：

```java
public class PropertiesToStringConverter implements ConditionalGenericConverter {
    @Override
    public boolean matches(TypeDescriptor sourceType, TypeDescriptor targetType) {
        return Properties.class.equals(sourceType.getObjectType()) && String.class.equals(targetType.getObjectType());
    }

    @Override
    public Set<ConvertiblePair> getConvertibleTypes() {
        return Collections.singleton(new ConvertiblePair(Properties.class, String.class));
    }

    @Override
    public Object convert(Object source, TypeDescriptor sourceType, TypeDescriptor targetType) {
        Properties properties = (Properties) source;
        StringBuilder textBuilder = new StringBuilder();
        for (Map.Entry<Object, Object> entry : properties.entrySet()) {
            textBuilder.append(entry.getKey()).append("=").append(entry.getValue()).append(System.getProperty("line.separator"));
        }
        return textBuilder.toString();
    }
}
```

步骤二：

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:util="http://www.springframework.org/schema/util"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
       http://www.springframework.org/schema/beans/spring-beans.xsd'
       http://www.springframework.org/schema/util
       http://www.springframework.org/schema/util/spring-util.xsd">

    <bean id="user" class="org.jyc.thinking.in.spring.ioc.overview.dependency.domain.User">
        <property name="id" value="1"/>
        <property name="name" value="胡先森"/>
        <property name="context"> <!-- Properties类型 -->
            <value>
                id = 1
                name = 胡先森
            </value>
        </property>
        <property name="contextAsText" ref="context"/> <!--properties类型要转成String -->
    </bean>

    <util:properties id="context">
        <prop key="id">1</prop>
        <prop key="name">jiyongchao</prop>
    </util:properties>

    <!-- 声明ConversionServiceFactoryBean-->
    <bean id="conversionService" class="org.springframework.context.support.ConversionServiceFactoryBean">
        <property name="converters" value="org.jyc.thinking.in.spring.conversion.PropertiesToStringConverter"/>
    </bean>
</beans>
```

> 需要格外注意的是，在注册 ConversionServiceFactoryBean 的时候，一定要指定名称为 conversionService，因为在 beanFactory 进行查找的时候，会根据名称和类型共同查找，名称固定为 conversionService。

## 统一类型转换服务

org.springframework.core.convert.ConversionService 说明：

| 实现类型                           | 说明                                                                                      |
| ---------------------------------- | ----------------------------------------------------------------------------------------- |
| GenericConversionService           | 通用 ConversionService 模板实现，不内置转化器实现                                         |
| DefaultConversionService           | 基础 ConversionService 实现，内置常用转化器实现                                           |
| FormattingConversionService        | 通用 Formatter + GenericConversionService 实现，不内置转化器和 Formatter 实现             |
| DefaultFormattingConversionService | DefaultConversionService + 格式化 实现（如：JSR-354 Money & Currency，JSR-310 Date-Time） |

## ConversionService 作为依赖

类型转换器底层接口 - org.springframework.beans.TypeConverter

- 起始版本：Spring 2.0
- 核心方法 - convertlfNecessary 重载方法
- 抽象实现 - org.springframework.beans.TypeConverterSupport
- 简单实现 - org.springframework.beans.SimpleTypeConverter

类型转换器底层抽象实现 - org.springframework.beans.TypeConverterSupport

- 实现接口 - org.springframework.beans.TypeConverter
- 扩展实现 - org.springframework.beans.PropertyEditorRegistrySupport
- 委派实现 - org.springframework.beans.TypeConverterDelegate

类型转换器底层委派实现 - org.springframework.beans.TypeConverterDelegate

- 构造来源 - org.springframework.beans.AbstractNestablePropertyAccessor 实现
  - org.springframework.beans.BeanWrapperImpl
- 依赖 - java.beans.PropertyEditor 实现
  - 默认内建时间 - org.springframework.beans.PropertyEditorRegistrySupport#registerDefaultEditors
- 可选依赖 - org.springframework.core.convert.ConversionService 实现

整体的流程关键节点如下：

> AbstractApplicationContext -> "conversionService" ConversionService Bean -> configurableBeanFactory#setConversionService(conversionService) -> AbstractAutowireCapableBeanFactory#instantiateBean -> AbstractBeanFactory#getConversionServicee -> BeanDefinition -> BeanWrapper -> 属性转换(数据来源：PropertyValues) -> setPropertyValues(PropertyValues) -> TypeConvert#convertIfNecessnary -> TypeConverterDelegate -> PropertyEditor or ConversionService

## 面试题

### Spring 类型转换实现有哪些？

1. 基于 JavaBeans PropertyEditor 接口实现
2. Spring 3.0+通用类型转换实现

### Spring 类型转换器接口有哪些？

- 类型转换接口 - org.springframework.core.convert.converter.Converter
- 通用类型转换接口 - org.springframework.core.convert.converter.GenericConverter
- 类型条件接口 - org.springframework.core.convert.converter.ConditionalConverter
- 综合类型转换接口 - org.springframework.core.convert.converter.ConditionalGenericConverter

### TypeDescriptor 是如何处理泛型？

// ...

# Spring 泛型

## Java 泛型基础

泛型类型：

- 泛型类型是在类型上参数化的泛型类或接口

泛型的使用场景：

- 编译时强制类型检查
- 避免类型强转
- 实现通用算法

泛型类型擦写：

- 泛型被引入到 Java 语言中，以便在编译时提供更严格的类型检查并支持泛型编程。类型擦除确保不会为参数化类型创建新类；因此，泛型不会产生运行时开销。为了实现泛型，编译器将类型擦除应用于：
  - 将泛型类型中的所有类型参数替换为其边界，如果类型参数是无边界的，则将其替换为"Object"。因为，生成的字节码只包含普通类、接口和方法
  - 必要时插入类型转换以保持类型安全
  - 生成桥方法以保留扩展泛型类中的多态性

## Java 5 类型接口

Java 5 类型接口 - java.lang.reflect.Type

| 派生类或接口                        | 说明                                  |
| ----------------------------------- | ------------------------------------- |
| java.lang.Class                     | Java 类 API，如 java.lang.String      |
| java.lang.reflect.GenericArrayType  | 泛型数组类型                          |
| java.lang.reflect.ParameterizedType | 泛型参数类型                          |
| java.lang.reflect.TypeVariable      | 泛型类型变量，如 Collection<E> 中的 E |
| java.lang.reflect.WildcardType      | 泛型统配类型                          |

Java 泛型反射 API：

| 类型     | API                                  |
| -------- | ------------------------------------ |
| 泛型信息 | java.lang.Class#getGenericInfo       |
| 泛型参数 | java.lang.reflect#ParameterizedType  |
| 泛型父类 | java.lang.Class#getGenericSuperclass |
| 泛型接口 | java.lang.Class#getGenericInterfaces |
| 泛型声明 | java.lang.reflect#GenericDeclaration |

相关的示例：

```java
public class GenericAPIDemo {
    public static void main(String[] args) {
        // 原生类型 int long float
        Class intClass = int.class;
        // 数组类型 int[],Object[]
        Class objectArrayClass = Object[].class;
        // 原始类型 raw types: java.lang.String
        Class rawClass = String.class;

        // 泛型参数类型 parameterized Type
        ParameterizedType parameterizedType = (ParameterizedType) ArrayList.class.getGenericSuperclass();

        // parameterizedType.getRawType() = java.util.AbstractList;

        //泛型类型变量 Type Variable

        System.out.println(parameterizedType.toString());

        // <E>
        Type[] typeVariables = parameterizedType.getActualTypeArguments();
//        Stream.of(parameterizedType.getActualTypeArguments()).forEach(System.out::println);
        Stream.of(typeVariables).map(TypeVariable.class::cast).forEach(System.out::println);
    }
}
```

## Spring 泛型类型辅助类

核心 API - org.springframework.core.GenericTypeResolver

- 版本支持[2.5.2,）

- 处理类型相关（Type）相关方法

  - resolveReturnType
  - resolveType

- 处理泛型参数类型（ParameterizedType）相关方法

  - resolveReturnTypeArgument
  - resolveTypeArgument
  - resolveTypeArguments

- 处理泛型类型变量（TypeVariable）相关方法

  - getTypeVariableMap

相关的示例：

```java
public class GenericTypeResolverDemo {
    public static void main(String[] args) throws Exception {
        // String Comparable<String> 具体化
        displayReturnTypeGenericInfo(GenericTypeResolverDemo.class, Comparable.class, "getString");
        // ArrayList<Object>是List泛型参数类型的具体化
        displayReturnTypeGenericInfo(GenericTypeResolverDemo.class, List.class, "getList");
        // StringList也是List泛型类型的具体化
        displayReturnTypeGenericInfo(GenericTypeResolverDemo.class, List.class, "getStringList");
        // 具备 ParameterizedType返回。否则null
        // TypeVariable
        Map<TypeVariable, Type> typeVariableMap = GenericTypeResolver.getTypeVariableMap(StringList.class);
        System.out.println(typeVariableMap);
    }

    public static StringList getStringList() {
        return null;
    }

    public static ArrayList<Object> getList() { // 泛型参数具体化（字节码有记录）
        return null;
    }

    public static String getString() {
        return null;
    }

    private static void displayReturnTypeGenericInfo(Class<?> containingClass, Class<?> generic, String methodName, Class... argumentTypes) throws Exception {
        Method method = containingClass.getMethod(methodName, argumentTypes);

        Class<?> returnType = GenericTypeResolver.resolveReturnType(method, containingClass);

        Class<?> returnTypeArgument = GenericTypeResolver.resolveReturnTypeArgument(method, generic);

        // 常规类作为方法返回值
        System.out.printf("GenericTypeResolver.resolveReturnType(%s,%s) = %s\n", methodName, containingClass.getSimpleName(), returnType);
        // 常规类型不具备泛型参数类型List<E>
        System.out.printf("GenericTypeResolver.resolveReturnTypeArgument(%s,%s) = %s\n", methodName, containingClass.getSimpleName(), returnTypeArgument);
    }

    static class StringList extends ArrayList<String> { // 泛型参数具体化（字节码有记录）

    }
}
```

## 泛型集合类型辅助类

核心 API - org.springframework.core.GenericCollectionTypeSolver

- 版本支持：[2.0,4.3]

  - 替换实现：org.springframework.core.ResolvableType

- 处理 Collection 相关

  - getCollection\*Type
  - getMapValue\*Type

  > GenericCollectionTypeSolver 在高版本的 Spring 中已经移除，建议使用它的替换实现 ResolvableType。

## Spring 方法参数封装

核心 API - org.springframework.core.MethodParameter

- 起始版本：[2.0,)

- 元信息

  - 关联的方法 - Method
  - 关联的构造器 - Constuctor
  - 构造器或方法参数索引 - parameterIndex
  - 构造器或方法参数类型 - parameterType
  - 构造器或方法参数泛型类型 - genericParameterType
  - 构造器或方法参数名称 - parameterName
  - 所在的类 - containingClass

  > parameterName 是 java8 之后才存在。

## ResolvableType

核心 API - org.springframework.core.ResolvableType

- 起始版本：[4.0,)
- 扮演角色：GenericTypeResolver 和 GenericCollectionTypeResolver 替代者
- 工厂方法：for\*方法
- 转换方法：as\*方法
- 处理方法：resolve\*方法

官方给出的示例：

```java
 private HashMap<Integer, List<String>> myMap;

   public void example() {
       ResolvableType t = ResolvableType.forField(getClass().getDeclaredField("myMap"));
       t.getSuperType(); // AbstractMap<Integer, List<String>>
       t.asMap(); // Map<Integer, List<String>>
       t.getGeneric(0).resolve(); // Integer
       t.getGeneric(1).resolve(); // List
       t.getGeneric(1); // List<String>
       t.resolveGeneric(1, 0); // String
   }
```

我们来使用相关的 API：

```java
public class ResolvableTypeDemo {
    public static void main(String[] args) throws Exception {
        // 工厂创建
        // StringList <- ArrayList <- AbstractList <- list
        ResolvableType resolvableType = ResolvableType.forClass(GenericTypeResolverDemo.StringList.class);
        resolvableType.getSuperType(); //ArrayList
        resolvableType.getSuperType().getSuperType(); // AbstractList

        System.out.println(resolvableType.asCollection().resolve()); //获取Raw Type
        System.out.println(resolvableType.asCollection().resolveGeneric(0)); // 获取泛型参数类型
    }
}
```

> ResolvableType 也有两个局限性，第一，ResolvableType 无法处理泛型擦写，第二，ResolvableType 无法处理非具体化的 ParameterizedType。

## 面试题

### Java 泛型擦写是发生在编译时，还是运行时？

运行时。

### 请介绍 Java 5 Type 类型的派生类或接口?

见 Java5 类型接口

### 请说明 ResolvableType 的设计优势

- 简化 Java5 Type API 开发，屏蔽复杂 API 的运用，如 ParameterizedType
- 不变性设计（Immutability）
- Fluent API 设计（Builder 模式），链式（流式）编程

# Spring 事件

## Java 事件/监听器编程模型

- 设计模式 - 观察者模式扩展
  - 可观者对象（消息发送者） - java.util.Observable
  - 观察者 - java.util.Observer
- 标准化接口
  - 事件对象 - java.util.EventObject
  - 事件监听器 - java.util.EventListener

使用的示例：

```java
public class ObserverDemo {
    public static void main(String[] args) {
        Observable observable = new EventObservable();
        // 添加观察者（监听者）
        observable.addObserver(new EventObserver());
        observable.notifyObservers("hello world");
    }

    static class EventObservable extends Observable {
        @Override
        public synchronized void setChanged() {
            super.setChanged();
        }

        @Override
        public void notifyObservers(Object arg) {
            setChanged();
            super.notifyObservers(new EventObject(arg));
            clearChanged();
        }
    }

    static class EventObserver implements Observer, EventListener {
        @Override
        public void update(Observable o, Object event) {
            EventObject eventObject = (EventObject) event;
            System.out.println("收到事件" + eventObject);
        }
    }
}
```

> 这里由于 Observable 的 setChanged 是 protected，所以需要实现子类，重写这个方法，并且为了更方便的操作，我们一般也会扩充 notifyObservers 的实现逻辑。

## 面向接口的事件/监听器设计模式

事件/监听器场景举例

| Java 技术规范   | 事件接口                              | 监听器接口                               |
| --------------- | ------------------------------------- | ---------------------------------------- |
| JavaBeans       | java.beans.PropertyChangeEvent        | java.beans.PropertyChangeListener        |
| Java AWT        | java.awt.event.MouseEvent             | java.awt.event.MouseListener             |
| Java Swing      | javax.swing.event.MenuEvent           | javax.swing.event.MenuListener           |
| Java Preference | java.util.prefs.PreferenceChangeEvent | java.util.prefs.PreferenceChangeListener |

## 面向注解的事件/监听器设计模式

事件/监听器注解场景举例

| Java 技术规范 | 事件注解                       | 监听器注解                            |
| ------------- | ------------------------------ | ------------------------------------- |
| Servlet 3.0+  |                                | @javax.servlet.annotation.WebListener |
| JPA 1.0+      | @javax.persistence.PostPersist |                                       |
| Java Common   | @PostConstruct                 |                                       |
| EJB 3.0+      | @javax.ejb.PrePassivate        |                                       |
| JSF 2.0+      | @javax.faces.event.ListenerFor |                                       |

## Spring 标准事件 ApplicationEvent

Java 标准事件 java.util.EventObject 扩展：

- 扩展特性：事件发生事件戳

Spring 应用上下文 ApplicationEvent 扩展 - ApplicationContextEvent

- Spring 应用上下文（ApplicationContext 作为事件源）
- 具体实现：
  - org.springframework.context.event.ContextClosedEvent
  - org.springframework.context.event.ContextRefreshedEvent
  - org.springframework.context.event.ContextStartedEvent
  - org.springframework.context.event.ContextStoppedEvent

## 基于接口的 Spring 事件监听器

Java 标准事件监听器 java.util.EventListener 扩展

- 扩展接口 - org.springframework.context.ApplicationListener
- 设计特点：单一类型事件处理
- 处理方法：onApplicationEvent(ApplicationEvent event);
- 事件类型：org.springframework.context.ApplicationEvent

相关的示例：

```java
public class ApplicationListenerDemo {
    public static void main(String[] args) {
        GenericApplicationContext context = new GenericApplicationContext();
        // 向Spring应用上下文注册事件
        context.addApplicationListener(new ApplicationListener<ApplicationEvent>() {
            @Override
            public void onApplicationEvent(ApplicationEvent event) {
                System.out.println("接收到Spring事件： " + event);
            }
        });
        context.refresh();
        context.start();
        context.close();
    }
}
```

## 基于注解的 Spring 事件监听器

Spring 注解 - @org.springframework.context.event.EventListener

| 特性                 | 说明                                       |
| -------------------- | ------------------------------------------ |
| 设计特点             | 支持多 ApplicationEvent 类型，无需接口约束 |
| 注解目标             | 方法                                       |
| 是否支持异步执行     | 支持                                       |
| 是否支持泛型类型事件 | 支持                                       |
| 是指支持顺序控制     | 支持，配合@Order 注解控制                  |

相关的示例：

```java
@EnableAsync
public class ApplicationListenerDemo {
    public static void main(String[] args) {
//        GenericApplicationContext context = new GenericApplicationContext();
        AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext();
        // 将引导类作为配置类
        context.register(ApplicationListenerDemo.class);
        // 方法一：基于Spring接口：向Spring应用上下文注册事件
        context.addApplicationListener(new ApplicationListener<ApplicationEvent>() {
            @Override
            public void onApplicationEvent(ApplicationEvent event) {
                println("ApplicationListene接收到Spring事件： " + event);
            }
        });
        // 方法二：基于Spring注解@EventListener

        context.refresh();
        context.start();
        context.close();
    }

    @EventListener
    @Order(1)
    public void onApplicationEvent(ContextRefreshedEvent event) {
       println("@EventListener1接收到Spring事件");
    }

    @EventListener
    @Order(2)
    public void onApplicationEvent1(ContextRefreshedEvent event) {
        println("@EventListener2接收到Spring事件");
    }

    @EventListener
    @Async
    public void onApplicationEvent(ContextStartedEvent event) {
        println("@EventListener接收到Spring事件（异步）");
    }

    @EventListener
    public void onApplicationEvent(ContextClosedEvent event) {
       println("@EventListener接收到Spring事件");
    }

    private static void println(Object printable) {
        System.out.printf("[线程：%s] : %s\n", Thread.currentThread(), printable);
    }
}
```

## 注册 Spring ApplicationListener

1. 方法一：ApplicationListener 作为 Spring Bean 注册
2. 方法二：通过 ConfigurableApplicationContext API 注册

第二种方式在之前我们已经讨论过了，这里第一种方式也比较容易：

```java
 static class MyApplicationListener implements ApplicationListener {
        @Override
        public void onApplicationEvent(ApplicationEvent event) {
            println("MyApplicationListener接收到Spring事件");
        }
    }
```

然后将 MyApplicationListener 标注为 Spring Bean 即可。

## Spring 事件发布器

- 方法一：通过 ApplicationEventPublisher 发布 Spring 事件
  - 获取 ApplicationEventPublisher
    - 依赖注入
- 方法二：通过 ApplicationEventPublisher 发布 Spring 事件
  - 获取 ApplicationEventMulticaster
    - 依赖注入
    - 依赖查找

使用 ApplicationListenerDemo 实现 ApplicationEventPublisherAware 接口：

```java
    @Override
    public void setApplicationEventPublisher(ApplicationEventPublisher applicationEventPublisher) {
        applicationEventPublisher.publishEvent(new ApplicationEvent("hello world") {
        });
        applicationEventPublisher.publishEvent("hello world");
    }
```

## Spring 层次性上下文事件传播

- 发生说明

  当 Spring 应用出现多层次 Spring 应用上下文（ApplicationContext）时，如 Spring WebMVC、Spring Boot 或 Spring Cloud 场景下，由子 ApplicationContext 发起 Spring 事件可能会传递到其 Parent ApplicationContext（直到 Root）的过程。

- 如何避免

  定位 Spring 事件源（ApplicationContext）进行过滤处理

```java
public class HierarchicalSpringEventPropagateDemo {
    public static void main(String[] args) {
        // 1.创建parent Spring应用上下文
        AnnotationConfigApplicationContext parentContent = new AnnotationConfigApplicationContext();
        // 2.创建current Spring应用上下文
        parentContent.setId("parent-context");
        parentContent.register(MyListener.class);

        // 3.current -> parent
        AnnotationConfigApplicationContext currentContent = new AnnotationConfigApplicationContext();
        parentContent.setId("current-context");
        currentContent.setParent(parentContent);
        currentContent.register(MyListener.class);

        parentContent.refresh();
        // 这里会触发两次，因为会出发父应用上下文的事件
        currentContent.refresh();

        // 注意这里的顺序，不能颠倒
        currentContent.close();
        parentContent.close();
    }

    static class MyListener implements ApplicationListener<ApplicationContextEvent> {
        // 这里必须是静态字段
        private static Set<ApplicationEvent> processedEvents = new LinkedHashSet<>();

        @Override
        public void onApplicationEvent(ApplicationContextEvent event) {
            if (processedEvents.add(event)) {
                System.out.printf("监听到 Spring应用上下文[ID：%s]事件： %s\n", event.getApplicationContext().getId(), event.getClass().getSimpleName());
            }
        }
    }
}
```

## Spring 内建事件

ApplicationContextEvent 派生事件：

- ContextRefreshedEvent：Spring 应用上下文就绪事件
- ContextStartedEvent：Spring 应用上下文启动事件
- ContextStoppedEvent：Spring 应用上下文停止事件
- ContextClosedEvent：Spring 应用上下文关闭事件

## Payload 事件

Spring Payload 事件 - org.springframework.context.PayloadApplicationEvent

- 使用场景：简化 Spring 事件发送，关注事件源主体
- 发送方法：ApplicationEventPublisher#publishEvent(Object event)

> 这个事件使用的很少，并且对于泛型的处理还存在 Bug，可以使用 ApplicationEventPublisher#publishEvent 方法。

## 自定义 Spring 事件

1. 扩展 org.springframework.context.ApplicationEvent
2. 实现 org.springframework.context.ApplicationListener
3. 注册 org.springframework.context.ApplicationListener

我们来实现一个自定义的 Spring 事件，第一步：

```java
public class MySpringEvent extends ApplicationEvent {

    public MySpringEvent(String message) {
        super(message);
    }

    @Override
    public Object getSource() {
        return (String) super.getSource();
    }

    @Override
    public String toString() {
        return super.toString();
    }
}
```

第二步，实现自定义的事件监听器：

```java
public class MySpringEventListener implements ApplicationListener<MySpringEvent> {
    @Override
    public void onApplicationEvent(MySpringEvent event) {
        System.out.printf("[线程：%s] :监听到事件 %s\n", Thread.currentThread().getName(), event);
    }
}
```

第三步，注册自定义事件监听器：

```java
public class CustomizedSpringEventDemo {
    public static void main(String[] args) {
        GenericApplicationContext context = new GenericApplicationContext();

        context.addApplicationListener(new MySpringEventListener());

        context.refresh();

        context.publishEvent(new MySpringEvent("hello,world"));

        context.close();
    }
}
```

## 依赖注入 ApplicationEventPublisher

1. 通过 ApplicationEventPublisherAware 回调接口
2. 通过@Autowired ApplicationEventPublisher

相关的示例：

```java
public class InjectingApplicationEventPublisherDemo implements ApplicationEventPublisherAware {

    @Autowired
    private ApplicationEventPublisher applicationEventPublisher;

    @Autowired
    private ApplicationContext applicationContext;

    @PostConstruct
    public void init() {
        // #3
        applicationEventPublisher.publishEvent(new MySpringEvent("the event from @Autowired ApplicationEventPublisher"));
        // #4
        applicationContext.publishEvent(new MySpringEvent("the event from @Autowired ApplicationContext"));
    }

    public static void main(String[] args) {
        AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext();

        context.register(InjectingApplicationEventPublisherDemo.class);

        context.addApplicationListener(new MySpringEventListener());

        context.refresh();

        context.close();
    }

    @Override
    public void setApplicationEventPublisher(ApplicationEventPublisher applicationEventPublisher) {
        applicationEventPublisher.publishEvent(new MySpringEvent("the event from ApplicationEventPublisher")); //#1
    }

    public void setApplicationContext(ApplicationContext applicationContext) { //#2
        applicationEventPublisher.publishEvent("the event from ApplicationContext");
    }
}
```

## 依赖查找 ApplicationEventMulticaster

查找条件：

- Bean 名称："applicationEventMulticaster"
- Bean 类型：org.springframework.context.event.ApplicationEventMulticaster

依赖查找的细节可以在 AbstractApplicationContext#initApplicationEventMulticaster 中看到：

```java
protected void initApplicationEventMulticaster() {
		ConfigurableListableBeanFactory beanFactory = getBeanFactory();
		if (beanFactory.containsLocalBean(APPLICATION_EVENT_MULTICASTER_BEAN_NAME)) {
			this.applicationEventMulticaster =
					beanFactory.getBean(APPLICATION_EVENT_MULTICASTER_BEAN_NAME, ApplicationEventMulticaster.class);
			if (logger.isTraceEnabled()) {
				logger.trace("Using ApplicationEventMulticaster [" + this.applicationEventMulticaster + "]");
			}
		}
		else {
               // 如果不存在会直接new一个，也就是说初始化之后，ApplicationEventMulticaster不会为空
			this.applicationEventMulticaster = new SimpleApplicationEventMulticaster(beanFactory);
			beanFactory.registerSingleton(APPLICATION_EVENT_MULTICASTER_BEAN_NAME, this.applicationEventMulticaster);
			if (logger.isTraceEnabled()) {
				logger.trace("No '" + APPLICATION_EVENT_MULTICASTER_BEAN_NAME + "' bean, using " +
						"[" + this.applicationEventMulticaster.getClass().getSimpleName() + "]");
			}
		}
	}
```

## ApplicationEventPublisher 底层实现

底层实现：

- 接口：org.springframework.context.event.ApplicationEventMulticaster
- 抽象类：org.springframework.context.event.AbstractApplicationEventMulticaster
- 实现类：org.springframework.context.event.SimpleApplicationEventMulticaster

> 早期的 Spring，ApplicationEventPublisherAware 与 BeanPostProcessor 不能同时使用，后面的版本采用了事件回放的机制修复了这个 BUG。

## 同步和异步 Spring 事件广播

基本实现类 - org.springframework.context.event.SimpleApplicationEventMulticaster

- 模式切换： setTaskExecutor(Executor taskExecutor)
  - 默认模式：同步
  - 异步模式：如 java.util.concurrent.ThreadPoolExecutor
- 设计缺陷：非基于接口契约编程

基于编码的同步和异步事件广播示例：

```java
public class AsyncEventHandlerDemo {

    public static void main(String[] args) {
        GenericApplicationContext context = new GenericApplicationContext();

        context.addApplicationListener(new MySpringEventListener());

        context.refresh(); // 初始化 ApplicationEventMulticaster

        // 依赖查找 ApplicationEventMulticaster
        ApplicationEventMulticaster applicationEventMulticaster = context.getBean(AbstractApplicationContext.APPLICATION_EVENT_MULTICASTER_BEAN_NAME, ApplicationEventMulticaster.class);

        if (applicationEventMulticaster instanceof SimpleApplicationEventMulticaster) {
            SimpleApplicationEventMulticaster simpleApplicationEventMulticaster = (SimpleApplicationEventMulticaster) applicationEventMulticaster;
            //切换 taskExecutor
            ExecutorService taskExecutor = Executors.newSingleThreadExecutor(new CustomizableThreadFactory("my-spring-event-thread-pool"));
            // 同步 -> 异步
            simpleApplicationEventMulticaster.setTaskExecutor(taskExecutor);

            // 添加ContextClosedEvent事件处理
            applicationEventMulticaster.addApplicationListener(new ApplicationListener<ContextClosedEvent>() {
                @Override
                public void onApplicationEvent(ContextClosedEvent event) {
                    if (!taskExecutor.isShutdown()) {
                        taskExecutor.shutdown();
                    }
                }
            });
        }

        context.publishEvent(new MySpringEvent("hello,world"));

        context.close();
    }
}
```

除了这种编码的方式，还可以通过注解的方式。

基于注解 - org.springframework.context.event.EventListener

- 模式切换
  - 默认模式：同步
  - 异步模式：标注@org.springframework.scheduling.annotation.Async
- 实现限制：无法直接实现同步/异步动态切换

基于注解方式的示例：

```java
@EnableAsync // 激活Spring异步特性
public class AnnotatedAsyncEventHandlerDemo {

    public static void main(String[] args) {
        AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext();

        context.register(AnnotatedAsyncEventHandlerDemo.class);

        context.addApplicationListener(new MySpringEventListener());

        context.refresh(); // 初始化 ApplicationEventMulticaster
        context.publishEvent(new MySpringEvent("hello,world"));

        context.close();
    }

    @EventListener
    @Async
    public void onEvent(MySpringEvent event) {
        System.out.printf("[线程：%s] : %s\n", Thread.currentThread().getName(), event);
    }

    @Bean
    public Executor taskExecutor() {
        ExecutorService taskExecutor = newSingleThreadExecutor(new CustomizableThreadFactory("my-spring-event-thread-pool-a"));
        return taskExecutor;
    }
}
```

## Spring 事件异常处理

Spring3.0 错误处理接口 - org.springframework.util.ErrorHandler

使用场景：

- Spring 事件（Events）
  - SimpleApplicationEventMulticaster Spring 4.1 开始支持
- Spring 本地调度（Scheduling）
  - org.springframework.scheduling.concurrent.ConcurrentTaskScheduler
  - org.springframework.scheduling.concurrent.ThreadPoolTaskScheduler

实现的核心代码在 SimpleApplicationEventMulticaster#invokeListener：

```java
protected void invokeListener(ApplicationListener<?> listener, ApplicationEvent event) {
		ErrorHandler errorHandler = getErrorHandler();
		if (errorHandler != null) {
			try {
				doInvokeListener(listener, event);
			}
			catch (Throwable err) {
				errorHandler.handleError(err);
			}
		}
		else {
			doInvokeListener(listener, event);
		}
	}
```

## Spring 事件/监听实现原理

核心类 - org.springframework.context.event.SimpleApplicationEventMulticaster

- 设计模式：观察者模式扩展
  - 被观察者 - org.springframework.context.ApplicationListener
    - API 添加
    - 依赖查找
  - 通知对象 - org.springframework.context.ApplicationEvent
- 执行模式：同步/异步
- 异常处理：org.springframework.util.ErrorHandler
- 泛型处理：org.springframework.core.ResolvableType

> 监听事件的时候，Spring 还会处理 ApplicationEvent 的子孙类，包含所有层次的事件。

## SpringBoot 事件

SpringBoot 事件

| 事件类型                            | 发生时机                               |
| ----------------------------------- | -------------------------------------- |
| ApplicationStartingEvent            | 当 SpringBoot 应用已启动时             |
| ApplicationStartedEvent             | 当 SpringBoot 应用已启动时             |
| ApplicationEnvironmentPreparedEvent | 当 SpringBoot Environment 实例已准备时 |
| ApplicationPreparedEvent            | 当 SpringBoot 应用预备时               |
| ApplicationReadyEvent               | 当 SpringBoot 应用完全可用时           |
| ApplicationFailedEvent              | 当 SpringBoot 应用启动失败时           |

SpringCloud 事件

| 事件类型                    | 发生时机                              |
| --------------------------- | ------------------------------------- |
| EnvironmentChangeEvent      | 当 Environment 示例配置属性发生变化时 |
| HeartbeatEvent              | 当 DiscoveryClient 客户端发送心跳时   |
| InstancePreRegisteredEvent  | 当服务实例注册前                      |
| InstanceRegisteredEvent     | 当服务实例注册后                      |
| RefreshEvent                | 当 RefreshEndpoint 被调用时           |
| RefreshScopedRefreshedEvent | 当 Refresh Scope Bean 刷新后          |

## 面试题

### Spring 事件核心接口/组件？

- Spring 事件 - org.springframework.context.ApplicationEvent
- Spring 事件监听器 - org.springframework.context.ApplicationListener
- Spring 事件发布器 - org.springframework.context.ApplicationEventPublisher
- Spring 事件广播器 - org.springframework.context.event.ApplicationEventMulticaster

## Spring 同步和异步事件处理的使用场景？

- Spring 同步事件 - 绝大部分 Spring 使用场景，如 ContextRefreshedEvent
- Spring 异步事件 - 主要 @EventListener 与@Async 配合，实现异步处理，不阻塞主线程，比如长时间的数据计算任务等。不要轻易调整 SimpleApplicationEventMulticaster 中关联的 taskExecutor 对象，除非使用者非常了解 Spring 事件机制，否则容易出现异常行为。

## @EventListener 的工作原理

// ...

# Spring 注解驱动

Spring 注解驱动的编程发展的大概历程：

1. 注解驱动的启蒙时代：Spring Framework 1.x
2. 注解驱动的过渡时代：Spring Framework 2.x
3. 注解驱动的黄金时代：Spring Framework 3.x
4. 注解驱动的完善时代：Spring Framework 4.x
5. 注解驱动的当下时代：Spring Framework 5.x

## Spring 核心注解场景分类

Spring 模式注解：

| Spring 注解    | 场景说明           | 起始版本 |
| -------------- | ------------------ | -------- |
| @Repository    | 数据仓库模式注解   | 2.0      |
| @Component     | 通用组件模式注解   | 2.5      |
| @Service       | 服务模式注解       | 2.5      |
| @Controller    | Web 控制器模式注解 | 2.5      |
| @Configuration | 配置类模式注解     | 3.0      |

装配注解：

| Spring 注解     | 场景说明                                    | 起始版本 |
| --------------- | ------------------------------------------- | -------- |
| @ImportResource | 替换 XML 元素<import>                       | 2.5      |
| @Import         | 导入 Configuration 类                       | 2.5      |
| @ComponentScan  | 扫描指定 package 下标注 Spring 模式注解的类 | 3.1      |

依赖注入注解：

| Spring 注解 | 场景说明                            | 起始版本 |
| ----------- | ----------------------------------- | -------- |
| @Autowired  | Bean 依赖注入，支持多种依赖查找方式 | 2.5      |
| @Qualifer   | 细粒度的@Autowired 依赖查找         | 2.5      |

## Spring 注解编程模型

编程模型概览：

- 元注解（Meta-Annotations）
- Spring 模式注解（Stereotype Annotations）
- Spring 组合注解（Composed Annotations）
- Spring 注解属性别名和覆盖（Attribute Aliases and Overrides）

## Spring 元注解

除了直接使用 JDK 定义好的注解，我们还可以自定义注解，在 JDK 1.5 中提供了 4 个标准的用来对注解类型进行注解的注解类，我们称之为 meta-annotation（元注解），他们分别是：

- @Target
- @Retention
- @Documented
- @Inherited

Target 注解的作用是描述注解的使用范围。Reteniton 注解的作用是，描述注解保留的时间范围（即：被描述的注解在它所修饰的类中可以被保留到何时）。Documented 注解的作用是，描述在使用 javadoc 工具为类生成帮助文档时是否要保留其注解信息。Inherited 注解的作用是，使被它修饰的注解具有继承性（如果某个类使用了被@Inherited 修饰的注解，则其子类将自动具有该注解）。

除了以上四种标准，还有我们之前提到过的@Repeatable。

## Spring 模式注解

模式注解是一种注解，这种注解是用于去声明应用中扮演"组件"角色的类，@Component 是一种通用的组件注解，标注这个注解的类会被 Spring 扫描。

> 由于注解无法像接口或者类一样继承，因此只能采用使用注解描述注解的方式。

@Component"派生性"原理：

- 核心组件 - org.springframework.context.annotation.ClassPathBeanDefinitionScanner
  - org.springframework.context.annotation.ClassPathScanningCandidateComponentProvider
- 资源处理 - org.springframework.core.io.support.ResourcePatternResolver
- 资源 - 类元信息
  - org.springframework.core.type.classreading.MetadataReaderFactory
- 类元信息 - org.springframework.core.type.ClassMetadata
  - ASM 实现 - org.springframework.core.type.classreading.ClassMetadataReadingVisitor
  - 反射实现 - org.springframework.core.type.StandardAnnotationMetadata
- 注解元信息 - org.springframework.core.type.AnnotationMetadata
  - ASM 实现 - org.springframework.core.type.classreading.AnnotationMetadataReadingVisitor
  - 反射实现 - org.springframework.core.type.StandardAnnotationMetadata

我们定义一个测试类：

```java
@MyComponent
public class TestClass {
}
```

定义一个具有"派生性"的注解：

```java
@Target(ElementType.TYPE)
@Retention(RetentionPolicy.RUNTIME)
@Component // 元注解，实现@Component
public @interface MyComponent {
}
```

测试是否生效：

```java
@ComponentScan(basePackages = "org.jyc.thinking.in.spring.annotation")
public class ComponentScanDemo {
    public static void main(String[] args) {
        AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext();

        context.register(ComponentScanDemo.class);

        context.refresh();
        // 从Spring 4.0开始支持多层次@Component派生
        TestClass bean = context.getBean(TestClass.class);
        System.out.println(bean);
        context.close();
    }
}
```

## Spring 组合注解

Spring 组合注解（Composed Annotations）中的元注允许是 Spring 模式注解（Stereotype Annotation）与其他 Spring 功能性注解的任意组合。

比较典型的例子就是在 SpringBoot 场景中的 SpringBootApplication：

```java
@Target(ElementType.TYPE)
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Inherited
@SpringBootConfiguration
@EnableAutoConfiguration
@ComponentScan(excludeFilters = { @Filter(type = FilterType.CUSTOM, classes = TypeExcludeFilter.class),
		@Filter(type = FilterType.CUSTOM, classes = AutoConfigurationExcludeFilter.class) })
public @interface SpringBootApplication {
}
```

## Spring 注解属性别名

注解属性的别名实际上总共有两种，一种是显性的别名，一种是隐性的别名。

显性的别名比较容易理解，在@ComponentScan 中：

```java
	@AliasFor("basePackages")
	String[] value() default {};

	@AliasFor("value")
	String[] basePackages() default {};
```

此时 basePackages 和 value 就互为显性别名，下面是隐性别名的例子：

```java
@Target(ElementType.TYPE)
@Retention(RetentionPolicy.RUNTIME)
@Documented
@ComponentScan
public @interface MyComponentScan {
    /**
     * 隐形别名,当被元标注的注解中的属性无法表达语义的时候，就需要额外增加attribute属性，如果没有attribute属性，就表示"继承" @AliasFor中的注解的属性
     * <p>
     * 是注解的一种"多态"，子注解提供了新的属性方法引用"父"（元）注解中的属性方法
     *
     * @return
     */
    @AliasFor(annotation = ComponentScan.class, attribute = "basePackages")
    String[] scanBasePackages() default {};

    /**
     * scanBasePackages -> @AliasFor ComponentScan.basePackages.value(显性别名)
     *
     * @AliasFor ComponentScan.basePackages.value 传递隐形别名,而且这种方式是支持多层次的
     */
//    @AliasFor(annotation = ComponentScan.class, attribute = "value")
//    String[] scanBasePackages() default {};
}
```

## Spring 注解属性覆盖

属性覆盖也有两种，一种是显性覆盖，一种是隐形覆盖：

```java
@Target(ElementType.TYPE)
@Retention(RetentionPolicy.RUNTIME)
@Documented
@MyComponentScan
public @interface MyComponentScan2 {

    @AliasFor(annotation = MyComponentScan.class, attribute = "scanBasePackages")
    String[] BasePackages() default {};

    /**
     * 隐形覆盖
     * 在@MyComponentScan中也有scanBasePackages属性，如果注解中存在同名的就会覆盖掉元标注注解中的属性
     *
     * @return
     */
    String[] scanBasePackages() default {};

    /**
     * 显性覆盖
     * packages覆盖了scanBasePackages 同时覆盖了@MyComponentScan.scanBasePackages
     *
     * @return
     */
    @AliasFor("scanBasePackages")
    String[] packages() default {};
}
```

## Spring @Enable 模块驱动

@Eanable 模块驱动是以@Enabke 为前缀的注解驱动编程模型。所谓"模块"是指具备相同领域的功能组件的集合，组合形成一个独立的单元，比如 Web MVC 模块、AspectJ 代理模块、Caching（缓存）模块、JMX（Java 扩展模块）、Async（异步处理）模块等。

举例说明：

- @EnableWebMvc
- @EnableTranscationManagement
- @EnableCaching
- @EnableMBeanExport
- @EnaleAsync

除了框架内建的这些实现，我们还可以自定义@Eanable 模块：

1. 驱动注解：@Enable\*\*\*
2. 导入注解：@Import 具体实现
3. 具体以下三种实现均可：
   - 基于 Configuration Class
   - 基于@ImportSelector
   - 基于@ImportBeanDefinitionRegistar 接口实现

首先演示第一种基于配置类实现，首先定义一个注解：

```java
@Target(ElementType.TYPE)
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Import(HelloWorldConfiguration.class)
public @interface EnableHelloWorld {
}
```

然后定义相对应的配置类：

```java
@Configuration
public class HelloWorldConfiguration {
    @Bean
    public String helloWorld() {
        return "HelloWorld";
    }
}
```

最后进行测试：

```java
@EnableHelloWorld
public class EnableModuleDemo { // 第一步：通过@Enable**命名
    public static void main(String[] args) {
        AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext();

        context.register(EnableModuleDemo.class);

        context.refresh();

        String bean = context.getBean("helloWorld", String.class);
        System.out.println(bean);
        context.close();
    }
}
```

第二种实现，首先定义 ImportSelector 的实现类：

```java
public class HelloWorldImportSelector implements ImportSelector {
    @Override
    public String[] selectImports(AnnotationMetadata importingClassMetadata) {
        return new String[]{"org.jyc.thinking.in.spring.annotation.HelloWorldConfiguration"};
    }
}
```

添加到@Enable 注解：

```java
@Target(ElementType.TYPE)
@Retention(RetentionPolicy.RUNTIME)
@Documented
// 第二步：通过@Import注解导入具体实现
//@Import(HelloWorldConfiguration.class)
// 方法二：通过@ImportSelector接口实现
@Import(HelloWorldImportSelector.class)
public @interface EnableHelloWorld {
}
```

第三种实现：

```java
public class HelloWorldImportBeanDefinitionRegistrar implements ImportBeanDefinitionRegistrar {
    @Override
    public void registerBeanDefinitions(AnnotationMetadata importingClassMetadata, BeanDefinitionRegistry registry) {
        AnnotatedGenericBeanDefinition beanDefinition = new AnnotatedGenericBeanDefinition(HelloWorldConfiguration.class);
        BeanDefinitionReaderUtils.registerWithGeneratedName(beanDefinition,registry);
    }
}
```

同样的，添加到@Enable 注解上面：

```java
@Target(ElementType.TYPE)
@Retention(RetentionPolicy.RUNTIME)
@Documented
// 第二步：通过@Import注解导入具体实现
//@Import(HelloWorldConfiguration.class)
// 方法二：通过@ImportSelector接口实现
//@Import(HelloWorldImportSelector.class)
//方法三：通过 ImportBeanDefinitionRegistrar
@Import(HelloWorldImportBeanDefinitionRegistrar.class)
public @interface EnableHelloWorld {
}
```

## Spring 条件注解

Spring 的条件注解主要有两种：

- 基于配置条件注解 - @org.springframework.context.annotation.Profile
  - 关联对象 - org.springframework.core.env.Environment
  - 实现变化：从 Spring 4.0 开始，@Profile 基于@Conditional 实现
- 基于编程条件注解 - org.springframework.context.annotation.Conditional
  - 关联对象 - org.springframework.context.annotation.Condition 具体实现

@Condtional 实现原理大致如下：

- 上下文对象 - org.springframework.context.annotation.ConditionContext
- 条件判断 - org.springframework.context.annotation.ConditionEvaluator
- 配置阶段 - org.springframework.context.annotation.ConfigurationCondition.ConfigurationPhase
- 判断入口 - org.springframework.context.annotation.ConfigurationClassPostProcessor
  - org.springframework.context.annotation.ConfigurationClassParser

Profile 注解的示例：

```java
public class ProfileDemo {
    public static void main(String[] args) {
        AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext();

        context.register(ProfileDemo.class);

        // 获取Environment对象
        ConfigurableEnvironment environment = context.getEnvironment();
        // 默认的Profiles = ["odd"]
        environment.setDefaultProfiles("odd");

        // 添加活跃的Profiles
        environment.setActiveProfiles("even");
        context.refresh();

        Integer number = context.getBean("number", Integer.class);
        System.out.println(number);
        context.close();
    }

    @Bean(name = "number")
    @Profile("odd")
    public Integer odd() {
        return 1;
    }

    @Bean(name = "number")
//    @Profile("even")
    @Conditional(EventProfileCondition.class)
    public Integer even() {
        return 2;
    }
}
```

实际上@Conditional 注解的使用也可能会用到 Profile 属性：

```java
public class EventProfileCondition implements Condition {
    @Override
    public boolean matches(ConditionContext context, AnnotatedTypeMetadata metadata) {
        // 条件上下文
        Environment environment = context.getEnvironment();
        return environment.acceptsProfiles("even");
    }
}
```

@Profile 在 Spring 4 当中的实现方式：

基于 org.springframework.context.annotation.Condition 接口实现：org.springframework.context.annotation.ProfileCondition，实现的源码如下：

```java
class ProfileCondition implements Condition {

	@Override
	public boolean matches(ConditionContext context, AnnotatedTypeMetadata metadata) {
		MultiValueMap<String, Object> attrs = metadata.getAllAnnotationAttributes(Profile.class.getName());
		if (attrs != null) {
			for (Object value : attrs.get("value")) {
				if (context.getEnvironment().acceptsProfiles(Profiles.of((String[]) value))) {
					return true;
				}
			}
			return false;
		}
		return true;
	}
}
```

## SpringBoot 和 SpringCloud 注解

SpringBoot 注解：

| 注解                     | 场景说明                 | 起始版本 |
| ------------------------ | ------------------------ | -------- |
| @SpringBootConfiguration | Spring Boot 配置类       | 1.4.0    |
| @SpringBootApplication   | Spring Boot 应用引导注解 | 1.2.0    |
| @EnableAutoConfiguration | Spring Boot 激活自动装配 | 1.0.0    |

SpringCloud 注解：

| 注解                    | 场景说明                            | 起始版本 |
| ----------------------- | ----------------------------------- | -------- |
| @SpringCloudApplication | Spring Cloud 应用引导注解           | 1.0.0    |
| @EnableDiscovertClient  | Spring Cloud 激活服务发现客户端注解 | 1.0.0    |
| @EnableCircuitBreaker   | Spring Cloud 激活熔断注解           | 1.0.0    |

## 面试题

### Spring 模式注解有哪些？

- @Compenent
- @Resository
- @Service
- @Controller
- @Configuration

### @EventListener 的工作原理？

源码导读 - org.springframework.context.event.EventListenerMethodProcessor

### @PropertySource 工作原理

// ...

# Spring Environment 抽象

Environment 接口主要有以下两个作用：

1. 统一的 Spring 配置属性管理

   SpringFramework 3.1 开始引入 Environment 抽象，它统一 Spring 配置属性的存储，包括占位符处理和类型转换，不仅完整地替换 PropertyPlaceholderConfigurer，而且还支持更丰富的配置属性源（PropertySource）

2. 条件化 Spring Bean 装配管理

   通过 Environment Profiles 信息，帮助 Spring 容器提供条件化地装配 Bean

## Environment 接口使用场景

- 用于属性占位符处理
- 用于转换 Spring 配置属性类型
- 用于存储 Spring 配置属性源（PropertySource）
- 用于 Profiles 状态维护

## Environment 占位符处理

不同 Spring 版本 Environment 对于占位符处理有所差异：

- Spring 3.1 前占位符处理
  - 组件：org.springframework.beans.factory.config.PropertyPlaceholderConfigurer
  - 接口：org.springframework.util.StringValueResolver
- Spring 3.1+占位符处理：
  - 组件：org.springframework.context.support.PropertySourcesPlaceholderConfigurer
  - 接口：org.springframework.beans.factory.config.EmbeddedValueResolver

我们可以来看以下具体地使用场景，首先定义一个 properties 文件：

```properties
user.id=11111
user.name=jjjj
user.city=HANGZHOU
```

紧接着定义需要注入的 Bean：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

<!--    <bean class="org.springframework.beans.factory.config.PropertyPlaceholderConfigurer">-->
<!--        <property name="location" value="classpath:/META-INF/default.properties"/>-->
<!--        <property name="fileEncoding" value="UTF-8"/>-->
<!--    </bean>-->

    <bean class="org.springframework.context.support.PropertySourcesPlaceholderConfigurer">
        <property name="location" value="classpath:/META-INF/default.properties"/>
        <property name="fileEncoding" value="UTF-8"/>
    </bean>

    <bean id="user" class="org.jyc.thinking.in.spring.ioc.overview.dependency.domain.User">
        <property name="id" value="${user.id}"/>
        <property name="name" value="${user.name}"/>
        <property name="city" value="${user.city}"/>
    </bean>
</beans>
```

最后观察输出：

```java
public class PropertyPlaceholderConfigurerDemo {
    public static void main(String[] args) {
        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("classpath:/META-INF/placeholders-resolver.xml");
        User user = context.getBean("user", User.class);
        System.out.println(user);
        context.close();
    }
}
```

可以看到占位符已经被成功的替换。

## 理解条件配置 Spring Profiles

Spring3.1 的条件配置：

- API：org.springframework.core.env.ConfigurableEnvironment
  - 修改：addActiveProfile(String)、SetActiveProfiles(String...)和 setDefaultProfiles(String....)
  - 获取：getActiveProfiles()和 getDefaultProfiles
  - 匹配：#acceptsProfiles(String...)和 acceptsProfiles(Profiles)
- 注解：org.springframework.context.annotation.Profile

> 在 Spring 当中，也可以通过`-Dspring.profiles.active`来修改当前的激活环境。

## 依赖注入 Environment

1. 注解注入：
   - 通过 EnvironmentAware 接口回调
   - 通过@Autowired 注入 Environment
2. 间接依赖注入：
   - 通过 ApplicationAware 接口回调
   - 通过@Autowired 注入 ApplicationContext

相关的示例：

```java
public class InjectingEnvironmentDemo implements EnvironmentAware, ApplicationContextAware {

    private ApplicationContext applicationContext;

    private Environment environment;

    @Autowired
    private Environment environment2;

    public static void main(String[] args) {
        AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext();
        context.register(InjectingEnvironmentDemo.class);
        context.refresh();
        InjectingEnvironmentDemo injectingEnvironmentDemo = context.getBean(InjectingEnvironmentDemo.class);
        System.out.println(injectingEnvironmentDemo.environment);

        System.out.println(injectingEnvironmentDemo.environment == injectingEnvironmentDemo.environment2);

        System.out.println(context == injectingEnvironmentDemo.applicationContext);

        System.out.println(injectingEnvironmentDemo.environment == context.getEnvironment());

        context.close();
    }

    @Override
    public void setEnvironment(Environment environment) {
        this.environment = environment;
    }

    @Override
    public void setApplicationContext(ApplicationContext applicationContext) throws BeansException {
        this.applicationContext = applicationContext;
    }
}
```

## 依赖查找 Environment

1. 直接依赖查找
   - 通过 org.springframework.context.ConfigurableApplicationContext#ENVIRONMENT_BEAN_NAME
2. 直接查找
   - 通过 org.springframework.context.ConfigurableApplicationContext#getEnvironment

相关的示例：

```java
public class LookupEnvironmentDemo implements EnvironmentAware {

    private Environment environment;


    public static void main(String[] args) {
        AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext();

        context.register(LookupEnvironmentDemo.class);

        context.refresh();

        LookupEnvironmentDemo injectingEnvironmentDemo = context.getBean(LookupEnvironmentDemo.class);

        // 通过Environment Bean名称依赖查找
        Environment environment = context.getBean(ConfigurableApplicationContext.ENVIRONMENT_BEAN_NAME, Environment.class);

        System.out.println(injectingEnvironmentDemo.environment);

        System.out.println(injectingEnvironmentDemo.environment == environment);


        context.close();
    }

    @Override
    public void setEnvironment(Environment environment) {
        this.environment = environment;
    }
}
```

> 可以发现依赖查找和依赖注入的 Environment 都是同一个，Environment 对象本身隶属于 ApplicationContext，但是在容器启动的时候，会注册一个单例的 Environment 对象到 BeanFactory 中。

## 依赖注入@Value

@Value 注解的实现类：org.springframework.beans.factory.annotation.AutowiredAnnotationBeanPostProcessor

## Spring 类型转换在 Environment 中的运用

Environment 底层实现：

- 底层实现 - org.springframework.core.env.PropertySourcesPropertyResolver
  - 核心方法 - convertValueIfNecessary
- 底层服务 - org.springframework.core.convert.ConversionService
  - 默认实现 - org.springframework.core.convert.support.DefaultConversionService

相关的核心源代码：

<img src="https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210625173747553.png" alt="image-20210625173747553" style="zoom: 67%;" />

## Spring 类型转换在@Value 中的运用

@Value 底层实现：

1. 底层实现：org.springframework.beans.factory.annotation.AutowiredAnnotationBeanPostProcessor
   - org.springframework.beans.factory.support.DefaultListableBeanFactory#doResolveDependency
2. 底层服务：org.springframework.beans.TypeConverter
   - 默认实现：org.springframework.beans.TypeConverterDelegate
     - java.beans.PropertyEditor
     - org.springframework.core.convert.ConversionService

相关的核心源代码：

<img src="https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210625174810362.png" alt="image-20210625174810362" style="zoom: 50%;" />

## Spring 配置属性源 PropertySource

- API
  - 单配置属性源：org.springframework.core.env.PropertySource
  - 多配置属性源：org.springframework.core.env.PropertySources
- 注解

  - 单配置属性源：org.springframework.context.annotation.PropertySource
  - 多配置属性源：org.springframework.context.annotation.PropertySources

- 关联

  - 存储对象：org.springframework.core.env.MutablePropertySources
  - 关联方法：org.springframework.core.env.ConfigurableEnvironment#getPropertySources

## Spring 内建的配置属性源

内建的 PropertySource:

| PropertySource 类型                                                  | 说明                      |
| -------------------------------------------------------------------- | ------------------------- |
| org.springframework.core.env.CommandLinePropertySource               | 命令行配置属性源          |
| org.springframework.jndi.JndiPropertySource                          | JNDI 配置属性源           |
| org.springframework.core.env.PropertiesPropertySource                | Properties 配置属性源     |
| org.springframework.web.context.support.ServletConfigPropertySource  | Servlet 配置属性源        |
| org.springframework.web.context.support.ServletContextPropertySource | ServletContext 配置属性源 |
| org.springframework.core.env.SystemEnvironmentPropertySource         | 环境变量配置属性源        |
| ......                                                               |                           |

## 基于注解扩展 Spring 配置属性源

@org.springframework.context.annotation.PropertySource 实现原理：

- 入口 - org.springframework.context.annotation.ConfigurationClassParser#doProcessConfigurationClass
  - org.springframework.context.annotation.ConfigurationClassParser#processPropertySource
- 4.3 新增语义
  - 配置属性字符编码 - encoding
  - org.springframework.core.io.support.PropertySourceFactory
- 适配对象 - org.springframework.core.env.CompositePropertySource

> 默认只支持 properties 格式的文件，可以通过 PropertySourceFactory 进行扩展。

## 基于 API 扩展 Spring 配置属性源

PropertySource 的配置实际上有两种类型：

- Spring 应用上下文启动前装配 PropertySource
- Spring 应用上下文启动后装配 PropertySource

基于 API 扩展的示例：

```java
public class EnvironmentPropertySourceChangeDemo {
    @Value("${user.name}")
    private String UserName; // 不具备动态更新地能力

    // propertySource(“first-property-source”) {user.name = 胡先森}
    // propertySource(Java System Properties) {user.name = jyc}

    public static void main(String[] args) {

        AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext();

        context.register(EnvironmentPropertySourceChangeDemo.class);

        // 在Spring应用上下文启动之前，调整Environment中的PropertySource
        ConfigurableEnvironment environment = context.getEnvironment();
        // 获取MutablePropertySources 对象
        MutablePropertySources propertySources = environment.getPropertySources();
        // 动态地插入PropertySource到PropertySources
        HashMap<String, Object> source = new HashMap<>();
        source.put("user.name", "胡先森");
        MapPropertySource propertySource = new MapPropertySource("first-property-source", source);
        propertySources.addFirst(propertySource);
        context.refresh();

        source.put("user.name", "007");
        EnvironmentPropertySourceChangeDemo environmentPropertySourceChangeDemo = context.getBean(EnvironmentPropertySourceChangeDemo.class);
        System.out.println(environmentPropertySourceChangeDemo.UserName);

        for (PropertySource ps : propertySources) {
            System.out.printf("PropertySource(name=%s),'user.name'属性=%s\n", ps.getName(), ps.getProperty("user.name"));
        }
        context.close();
    }
}
```

## Spring 测试配置属性源

Spring 4.1 测试配置属性源 - @TestPropertySource

相关的示例：

```java
@RunWith(SpringRunner.class)
@ContextConfiguration(classes = TestPropertySourceDemo.class) //Spring 注解驱动测试注解
@TestPropertySource(properties = "user.name=胡先森")  // PropertySource(name=Inlined Test Properties)
public class TestPropertySourceDemo {
    @Value("${user.name}")
    private String userName;

    @Autowired
    private ConfigurableEnvironment environment;

    @Test
    public void testUserName() {
        System.out.println(new TestPropertySourceDemo().userName);
        for (PropertySource ps : environment.getPropertySources()) {
            System.out.printf("PropertySource(name=%s),'user.name'属性=%s\n", ps.getName(), ps.getProperty("user.name"));
        }
    }
}

```

可以看到@TestPropertySource 来源的优先级相当的高。

## 面试题

### 简单介绍 Spring Environment 接口？

- 核心接口 - org.springframework.core.env.Environment
- 父接口 - org.springframework.core.env.PropertyResolver
- 可配置接口 - org.springframework.core.env.ConfigurableEnvironment
- 职责：
  - 管理 Spring 配置属性源
  - 管理 Profiles

### 如何控制 PropertySource 的优先级？

可以通过相关的 Spring 相关的 API 进行操作

### Environment 完整的生命周期是怎样的？

// ...

# Spring 应用上下文生命周期

## Spring 应用上下文启动准备阶段

org.springframework.context.support.AbstractApplicationContext#prepareRefresh 方法：

- 启动时间 - startupDate
- 状态标志 - closed(false)、active(true)
- 初始化 PropertySources - initPropertySources()
- 校验 Environment 中必须属性
- 初始化事件监听器集合
- 初始化早期 Spring 事件集合

相关的源代码：

```java
	protected void prepareRefresh() {
		// Switch to active.
		this.startupDate = System.currentTimeMillis();
		this.closed.set(false);
		this.active.set(true);

		// Initialize any placeholder property sources in the context environment.
		initPropertySources();

		// Validate that all properties marked as required are resolvable:
		// see ConfigurablePropertyResolver#setRequiredProperties
		getEnvironment().validateRequiredProperties();

		// Store pre-refresh ApplicationListeners...
		if (this.earlyApplicationListeners == null) {
			this.earlyApplicationListeners = new LinkedHashSet<>(this.applicationListeners);
		}
		else {
			// Reset local application listeners to pre-refresh state.
			this.applicationListeners.clear();
			this.applicationListeners.addAll(this.earlyApplicationListeners);
		}

		// Allow for the collection of early ApplicationEvents,
		// to be published once the multicaster is available...
		this.earlyApplicationEvents = new LinkedHashSet<>();
	}
```

## BeanFactory 创建阶段

AbstractApplicationContext#obtainFreshBeanFactory 方法：

- 刷新 Spring 应用上下文底层 BeanFactory - refreshBeanFactory()
  - 销毁或关闭 BeanFactory，如果已存在的话
  - 创建 BeanFactory - createBeanFactory()
  - 设置 BeanFactory Id
  - 设置"是否允许 BeanDefinition 重复定义" - customizeBeanFactory(DefaultListableBeanFactory)
  - 设置"是否允许循环应用（依赖）" - customizeBeanFactory(DefaultListableBeanFactory)
  - 加载 BeanDefinition - loadBeanDefinitions(DefaultListableBeanFactory beanFactory)
  - 关联新建 BeanFactory 到 Spring 应用上下文
- 返回 Spring 应用上下文底层 BeanFactory - getBeanFactory

可以在 AbstractRefreshableApplicationContext 看到具体的实现：

```java
	@Override
	protected final void refreshBeanFactory() throws BeansException {
		if (hasBeanFactory()) {
			destroyBeans();
			closeBeanFactory();
		}
		try {
			DefaultListableBeanFactory beanFactory = createBeanFactory();
			beanFactory.setSerializationId(getId());
			customizeBeanFactory(beanFactory);
			loadBeanDefinitions(beanFactory);
			this.beanFactory = beanFactory;
		}
		catch (IOException ex) {
			throw new ApplicationContextException("I/O error parsing bean definition source for " + getDisplayName(), ex);
		}
	}
```

## BeanFactory 准备阶段

AbstractApplicationContext#prepareBeanFactory(ConfigurableListableBeanFactory)方法：

- 关联 ClassLoader
- 设置 Bean 表达式处理器
- 添加 PropertyEdittorRegistrar 实现 - ResourceEditorRegistrar
- 添加 Aware 回调接口 BeanPostProcessor 实现 - ApplicationContextAwareProcessor
- 忽略 Aware 回调接口作为依赖注入接口
- 注册 ResolvableDependency 对象 - BeanFactory、ResourceLoader、ApplicationEventPublisher 以及 ApplicationContext
- 注册 ApplicationListenerDetector 对象
- 注册 LoadTimeWeaverAwareProcessor 对象
- 注册单例对象 - Environment、Java System Properties、以及 OS 环境变量

相关的源代码：

```java
	protected void prepareBeanFactory(ConfigurableListableBeanFactory beanFactory) {
		// Tell the internal bean factory to use the context's class loader etc.
		beanFactory.setBeanClassLoader(getClassLoader());
		if (!shouldIgnoreSpel) {
			beanFactory.setBeanExpressionResolver(new StandardBeanExpressionResolver(beanFactory.getBeanClassLoader()));
		}
		beanFactory.addPropertyEditorRegistrar(new ResourceEditorRegistrar(this, getEnvironment()));

		// Configure the bean factory with context callbacks.
		beanFactory.addBeanPostProcessor(new ApplicationContextAwareProcessor(this));
		beanFactory.ignoreDependencyInterface(EnvironmentAware.class);
		beanFactory.ignoreDependencyInterface(EmbeddedValueResolverAware.class);
		beanFactory.ignoreDependencyInterface(ResourceLoaderAware.class);
		beanFactory.ignoreDependencyInterface(ApplicationEventPublisherAware.class);
		beanFactory.ignoreDependencyInterface(MessageSourceAware.class);
		beanFactory.ignoreDependencyInterface(ApplicationContextAware.class);
		beanFactory.ignoreDependencyInterface(ApplicationStartupAware.class);

		// BeanFactory interface not registered as resolvable type in a plain factory.
		// MessageSource registered (and found for autowiring) as a bean.
		beanFactory.registerResolvableDependency(BeanFactory.class, beanFactory);
		beanFactory.registerResolvableDependency(ResourceLoader.class, this);
		beanFactory.registerResolvableDependency(ApplicationEventPublisher.class, this);
		beanFactory.registerResolvableDependency(ApplicationContext.class, this);

		// Register early post-processor for detecting inner beans as ApplicationListeners.
		beanFactory.addBeanPostProcessor(new ApplicationListenerDetector(this));

		// Detect a LoadTimeWeaver and prepare for weaving, if found.
		if (!NativeDetector.inNativeImage() && beanFactory.containsBean(LOAD_TIME_WEAVER_BEAN_NAME)) {
			beanFactory.addBeanPostProcessor(new LoadTimeWeaverAwareProcessor(beanFactory));
			// Set a temporary ClassLoader for type matching.
			beanFactory.setTempClassLoader(new ContextTypeMatchClassLoader(beanFactory.getBeanClassLoader()));
		}

		// Register default environment beans.
		if (!beanFactory.containsLocalBean(ENVIRONMENT_BEAN_NAME)) {
			beanFactory.registerSingleton(ENVIRONMENT_BEAN_NAME, getEnvironment());
		}
		if (!beanFactory.containsLocalBean(SYSTEM_PROPERTIES_BEAN_NAME)) {
			beanFactory.registerSingleton(SYSTEM_PROPERTIES_BEAN_NAME, getEnvironment().getSystemProperties());
		}
		if (!beanFactory.containsLocalBean(SYSTEM_ENVIRONMENT_BEAN_NAME)) {
			beanFactory.registerSingleton(SYSTEM_ENVIRONMENT_BEAN_NAME, getEnvironment().getSystemEnvironment());
		}
		if (!beanFactory.containsLocalBean(APPLICATION_STARTUP_BEAN_NAME)) {
			beanFactory.registerSingleton(APPLICATION_STARTUP_BEAN_NAME, getApplicationStartup());
		}
	}
```

## BeanFactory 后置处理阶段

AbstractApplicationContext#postProcessBeanFactory(ConfigurableListableBeanFactory)方法

- 由子类覆盖该方法

AbstractApplicationContext#invokeBeanFactoryPostProcessors(ConfigurableListableBeanFactory)方法：

- 调用 BeanFactoryPostProcessor 或 BeanDefinitionPostProcessorRegistry 后置处理方法
- 注册 LoadTimeWeaverAwareProcessor 对象

> 通常情况下，我们应该选择第二种方式，组合优先于继承。

相关的源代码：

```java
protected void invokeBeanFactoryPostProcessors(ConfigurableListableBeanFactory beanFactory) {
		PostProcessorRegistrationDelegate.invokeBeanFactoryPostProcessors(beanFactory, getBeanFactoryPostProcessors());

		// Detect a LoadTimeWeaver and prepare for weaving, if found in the meantime
		// (e.g. through an @Bean method registered by ConfigurationClassPostProcessor)
		if (!NativeDetector.inNativeImage() && beanFactory.getTempClassLoader() == null && beanFactory.containsBean(LOAD_TIME_WEAVER_BEAN_NAME)) {
			beanFactory.addBeanPostProcessor(new LoadTimeWeaverAwareProcessor(beanFactory));
			beanFactory.setTempClassLoader(new ContextTypeMatchClassLoader(beanFactory.getBeanClassLoader()));
		}
	}
```

## BeanFactory 注册 BeanPostProcess

AbstractApplicationContext#registerBeanPostProcessors(ConfigurableListableBeanFactory beanFactory)方法：

- 注册 PriorityOrdered 类型的 BeanPostProcessor Beans
- 注册 Ordered 类型的 BeanPostProcessor Beans
- 注册普通 BeanPostProcessor Beans
- 注册 MergedBeanDefinitionPostProcessor Beans
- 注册 ApplicationListenerDetector 对象

相应的源代码：

```java
public static void registerBeanPostProcessors(
			ConfigurableListableBeanFactory beanFactory, AbstractApplicationContext applicationContext) {

		String[] postProcessorNames = beanFactory.getBeanNamesForType(BeanPostProcessor.class, true, false);

		// Register BeanPostProcessorChecker that logs an info message when
		// a bean is created during BeanPostProcessor instantiation, i.e. when
		// a bean is not eligible for getting processed by all BeanPostProcessors.
		int beanProcessorTargetCount = beanFactory.getBeanPostProcessorCount() + 1 + postProcessorNames.length;
		beanFactory.addBeanPostProcessor(new BeanPostProcessorChecker(beanFactory, beanProcessorTargetCount));

		// Separate between BeanPostProcessors that implement PriorityOrdered,
		// Ordered, and the rest.
		List<BeanPostProcessor> priorityOrderedPostProcessors = new ArrayList<>();
		List<BeanPostProcessor> internalPostProcessors = new ArrayList<>();
		List<String> orderedPostProcessorNames = new ArrayList<>();
		List<String> nonOrderedPostProcessorNames = new ArrayList<>();
		for (String ppName : postProcessorNames) {
			if (beanFactory.isTypeMatch(ppName, PriorityOrdered.class)) {
                    // 特别要注意，这里会导致Bean的提前初始化
				BeanPostProcessor pp = beanFactory.getBean(ppName, BeanPostProcessor.class);
				priorityOrderedPostProcessors.add(pp);
				if (pp instanceof MergedBeanDefinitionPostProcessor) {
					internalPostProcessors.add(pp);
				}
			}
			else if (beanFactory.isTypeMatch(ppName, Ordered.class)) {
				orderedPostProcessorNames.add(ppName);
			}
			else {
				nonOrderedPostProcessorNames.add(ppName);
			}
		}

		// First, register the BeanPostProcessors that implement PriorityOrdered.
		sortPostProcessors(priorityOrderedPostProcessors, beanFactory);
		registerBeanPostProcessors(beanFactory, priorityOrderedPostProcessors);

		// Next, register the BeanPostProcessors that implement Ordered.
		List<BeanPostProcessor> orderedPostProcessors = new ArrayList<>(orderedPostProcessorNames.size());
		for (String ppName : orderedPostProcessorNames) {
               // 这里也会初始化
			BeanPostProcessor pp = beanFactory.getBean(ppName, BeanPostProcessor.class);
			orderedPostProcessors.add(pp);
			if (pp instanceof MergedBeanDefinitionPostProcessor) {
				internalPostProcessors.add(pp);
			}
		}
		sortPostProcessors(orderedPostProcessors, beanFactory);
		registerBeanPostProcessors(beanFactory, orderedPostProcessors);

		// Now, register all regular BeanPostProcessors.
		List<BeanPostProcessor> nonOrderedPostProcessors = new ArrayList<>(nonOrderedPostProcessorNames.size());
		for (String ppName : nonOrderedPostProcessorNames) {
			BeanPostProcessor pp = beanFactory.getBean(ppName, BeanPostProcessor.class);
			nonOrderedPostProcessors.add(pp);
			if (pp instanceof MergedBeanDefinitionPostProcessor) {
				internalPostProcessors.add(pp);
			}
		}
		registerBeanPostProcessors(beanFactory, nonOrderedPostProcessors);

		// Finally, re-register all internal BeanPostProcessors.
		sortPostProcessors(internalPostProcessors, beanFactory);
		registerBeanPostProcessors(beanFactory, internalPostProcessors);

		// Re-register post-processor for detecting inner beans as ApplicationListeners,
		// moving it to the end of the processor chain (for picking up proxies etc).
		beanFactory.addBeanPostProcessor(new ApplicationListenerDetector(applicationContext));
	}
```

## 初始化内建 MessageSource

AbstractApplicationContext#initMessageSource 方法：

- 第十二章 Spring 国际化 - MessageSource 内建依赖

相应的源代码：

```java
	protected void initMessageSource() {
		ConfigurableListableBeanFactory beanFactory = getBeanFactory();
		if (beanFactory.containsLocalBean(MESSAGE_SOURCE_BEAN_NAME)) {
			this.messageSource = beanFactory.getBean(MESSAGE_SOURCE_BEAN_NAME, MessageSource.class);
			// Make MessageSource aware of parent MessageSource.
			if (this.parent != null && this.messageSource instanceof HierarchicalMessageSource) {
				HierarchicalMessageSource hms = (HierarchicalMessageSource) this.messageSource;
				if (hms.getParentMessageSource() == null) {
					// Only set parent context as parent MessageSource if no parent MessageSource
					// registered already.
					hms.setParentMessageSource(getInternalParentMessageSource());
				}
			}
			if (logger.isTraceEnabled()) {
				logger.trace("Using MessageSource [" + this.messageSource + "]");
			}
		}
		else {
			// Use empty MessageSource to be able to accept getMessage calls.
			DelegatingMessageSource dms = new DelegatingMessageSource();
			dms.setParentMessageSource(getInternalParentMessageSource());
			this.messageSource = dms;
			beanFactory.registerSingleton(MESSAGE_SOURCE_BEAN_NAME, this.messageSource);
			if (logger.isTraceEnabled()) {
				logger.trace("No '" + MESSAGE_SOURCE_BEAN_NAME + "' bean, using [" + this.messageSource + "]");
			}
		}
	}
```

## 初始化内建 Spring 事件广播器

AbstractApplicationContext#initApplicationEventMulticaster 方法：

- 第十七章 Spring 事件 - ApplicationEventMulticaster 底层实现

相应的源代码：

```java
protected void initApplicationEventMulticaster() {
		ConfigurableListableBeanFactory beanFactory = getBeanFactory();
		if (beanFactory.containsLocalBean(APPLICATION_EVENT_MULTICASTER_BEAN_NAME)) {
			this.applicationEventMulticaster =
					beanFactory.getBean(APPLICATION_EVENT_MULTICASTER_BEAN_NAME, ApplicationEventMulticaster.class);
			if (logger.isTraceEnabled()) {
				logger.trace("Using ApplicationEventMulticaster [" + this.applicationEventMulticaster + "]");
			}
		}
		else {
			this.applicationEventMulticaster = new SimpleApplicationEventMulticaster(beanFactory);
			beanFactory.registerSingleton(APPLICATION_EVENT_MULTICASTER_BEAN_NAME, this.applicationEventMulticaster);
			if (logger.isTraceEnabled()) {
				logger.trace("No '" + APPLICATION_EVENT_MULTICASTER_BEAN_NAME + "' bean, using " +
						"[" + this.applicationEventMulticaster.getClass().getSimpleName() + "]");
			}
		}
	}
```

> 可以看到在 Spring 的应用上下文中，ApplicationEventMulticaster 这个对象一定会存在，因此我们可以使用依赖注入的方式获取到唯一的对象 ApplicationEventMulticaster 的对象。

## Spring 应用上下文刷新

AbstractApplicationContext#onRefresh 方法：

- org.springframework.web.context.support.AbstractRefreshableWebApplicationContext#onRefresh
- org.springframework.web.context.support.GenericWebApplicationContext#onRefresh
- org.springframework.boot.web.reactive.context.ReactiveWebServerApplicationContext#onRefresh
- org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext#onRefresh
- org.springframework.web.context.support.StaticWebApplicationContext#onRefresh

> onRefresh()方法只有在 Web 的场景下才会进行扩展。

## Spring 事件监听器注册

AbstractApplicationContext#registerListeners 方法：

- 添加当前应用上下文所关联的 ApplicationListeners 对象（集合）
- 添加 BeanFactory 所注册 ApplicationListeners Beans
- 广播早期 Spring 事件

相应的源代码：

```java
protected void registerListeners() {
		// Register statically specified listeners first.
		for (ApplicationListener<?> listener : getApplicationListeners()) {
			getApplicationEventMulticaster().addApplicationListener(listener);
		}

		// Do not initialize FactoryBeans here: We need to leave all regular beans
		// uninitialized to let post-processors apply to them!
		String[] listenerBeanNames = getBeanNamesForType(ApplicationListener.class, true, false);
		for (String listenerBeanName : listenerBeanNames) {
			getApplicationEventMulticaster().addApplicationListenerBean(listenerBeanName);
		}

		// Publish early application events now that we finally have a multicaster...
		Set<ApplicationEvent> earlyEventsToProcess = this.earlyApplicationEvents;
		this.earlyApplicationEvents = null;
		if (!CollectionUtils.isEmpty(earlyEventsToProcess)) {
			for (ApplicationEvent earlyEvent : earlyEventsToProcess) {
				getApplicationEventMulticaster().multicastEvent(earlyEvent);
			}
		}
	}
```

## BeanFactory 初始化完成阶段

AbstractApplicationContext#finishBeanFactoryInitialization(ConfigurableListableBeanFactory)方法：

- BeanFactory 关联 ConversionService Bean，如果存在
- 添加 StringValueResolver 对象
- 依赖查找 LoadTimeWeaverAware Bean
- BeanFactory 临时 ClassLoader 置为 null
- BeanFactory 冻结配置
- BeanFactory 初始化非延迟单例 Beans

相应的源代码：

```java
	protected void finishBeanFactoryInitialization(ConfigurableListableBeanFactory beanFactory) {
		// Initialize conversion service for this context.
		if (beanFactory.containsBean(CONVERSION_SERVICE_BEAN_NAME) &&
				beanFactory.isTypeMatch(CONVERSION_SERVICE_BEAN_NAME, ConversionService.class)) {
			beanFactory.setConversionService(
					beanFactory.getBean(CONVERSION_SERVICE_BEAN_NAME, ConversionService.class));
		}

		// Register a default embedded value resolver if no BeanFactoryPostProcessor
		// (such as a PropertySourcesPlaceholderConfigurer bean) registered any before:
		// at this point, primarily for resolution in annotation attribute values.
		if (!beanFactory.hasEmbeddedValueResolver()) {
			beanFactory.addEmbeddedValueResolver(strVal -> getEnvironment().resolvePlaceholders(strVal));
		}

		// Initialize LoadTimeWeaverAware beans early to allow for registering their transformers early.
		String[] weaverAwareNames = beanFactory.getBeanNamesForType(LoadTimeWeaverAware.class, false, false);
		for (String weaverAwareName : weaverAwareNames) {
			getBean(weaverAwareName);
		}

		// Stop using the temporary ClassLoader for type matching.
		beanFactory.setTempClassLoader(null);

		// Allow for caching all bean definition metadata, not expecting further changes.
		beanFactory.freezeConfiguration();

		// Instantiate all remaining (non-lazy-init) singletons.
		beanFactory.preInstantiateSingletons();
	}
```

## Spring 应用上下文刷新完成阶段

AbstractApplicationContext#finishRefresh 方法：

- 清除 ResourceLoader 缓存 - clearResourceCaches() @since 5.0
- 初始化 LifecycleProcessor 对象 - initLifecycleProcessor()
- 调用 LifecycleProcessor().onRefresh()方法
- 发布 Spring 应用上下文已刷新事件 - ContextRefreshedEvent
- 向 MBeanServer 托管 Live Beans

相应的源代码：

```java
protected void finishRefresh() {
		// Clear context-level resource caches (such as ASM metadata from scanning).
		clearResourceCaches();

		// Initialize lifecycle processor for this context.
		initLifecycleProcessor();

		// Propagate refresh to lifecycle processor first.
		getLifecycleProcessor().onRefresh();

		// Publish the final event.
		publishEvent(new ContextRefreshedEvent(this));

		// Participate in LiveBeansView MBean, if active.
		if (!NativeDetector.inNativeImage()) {
			LiveBeansView.registerApplicationContext(this);
		}
	}
```

## Spring 应用上下文启动阶段

AbstractApplicationContext#start 方法

- 启动 LifecycleProcessor
  - 依赖查找 Lifecycle Beans
  - 启动 Lifecycle Beans
- 发布 Spring 应用上下文已启动事件 - ContextStartedEvent

相应的源代码：

```java
public void start() {
		getLifecycleProcessor().start();
		publishEvent(new ContextStartedEvent(this));
	}
```

## Spring 应用上下文停止阶段

AbstractApplicationContext#stop 方法

- 停止 LifecycleProcessor
  - 依赖查找 Lifecycle Beans
  - 停止 Lifecycle Beans
- 发布 Spring 应用上下文已停止事件 - ContextStoppedEvent

相应的源代码：

```java
public void stop() {
		getLifecycleProcessor().stop();
		publishEvent(new ContextStoppedEvent(this));
	}
```

我们可以自定义一个 Lifecycle：

```java
public class MyLifecycle implements Lifecycle {

    private boolean running = false;

    @Override
    public void start() {
        running = true;
        System.out.println("org.jyc.thinking.in.spring.lifecycle.MyLifecycle 启动...");
    }

    @Override
    public void stop() {
        running = false;
        System.out.println("org.jyc.thinking.in.spring.lifecycle.MyLifecycle 停止...");
    }

    @Override
    public boolean isRunning() {
        return running;
    }
}
```

测试输出：

```java
public class LifecycleDemo {
    public static void main(String[] args) {
        GenericApplicationContext context = new GenericApplicationContext();
        // 注册MyLifecycle成为一个Spring Bean
        context.registerBeanDefinition("myLifecycle", BeanDefinitionBuilder.rootBeanDefinition(MyLifecycle.class).getBeanDefinition());
        context.refresh();
        // 启动应用上下文
        context.start();
        // 关闭Spring应用
        context.stop();
        context.close();
    }
}
```

## Spring 应用上下文关闭阶段

AbstractApplicationContext#close 方法:

- 状态标识：active(false)、closed(true)
- Live Beans JMX 撤销托管
  - LiveBeansView.unregisterApplicationContext(ConfigurableApplicationContext)
- 发布 Spring 应用上下文已关闭事件 - ContextClosedEvent
- 关闭 LifecycleProcessor
  - 依赖查找 Lifecycle Beans
  - 停止 Lifecycle Beans
- 销毁 Lifecycle Beans
- 关闭 BeanFactory
- 回调 onClose()
- 注册 Shutdown Hook 线程（如果曾注册）

相应的源代码：

```java
	protected void doClose() {
		// Check whether an actual close attempt is necessary...
		if (this.active.get() && this.closed.compareAndSet(false, true)) {
			if (logger.isDebugEnabled()) {
				logger.debug("Closing " + this);
			}

			if (!NativeDetector.inNativeImage()) {
				LiveBeansView.unregisterApplicationContext(this);
			}

			try {
				// Publish shutdown event.
				publishEvent(new ContextClosedEvent(this));
			}
			catch (Throwable ex) {
				logger.warn("Exception thrown from ApplicationListener handling ContextClosedEvent", ex);
			}

			// Stop all Lifecycle beans, to avoid delays during individual destruction.
			if (this.lifecycleProcessor != null) {
				try {
					this.lifecycleProcessor.onClose();
				}
				catch (Throwable ex) {
					logger.warn("Exception thrown from LifecycleProcessor on context close", ex);
				}
			}

			// Destroy all cached singletons in the context's BeanFactory.
			destroyBeans();

			// Close the state of this context itself.
			closeBeanFactory();

			// Let subclasses do some final clean-up if they wish...
			onClose();

			// Reset local application listeners to pre-refresh state.
			if (this.earlyApplicationListeners != null) {
				this.applicationListeners.clear();
				this.applicationListeners.addAll(this.earlyApplicationListeners);
			}

			// Switch to inactive.
			this.active.set(false);
		}
	}
```

这里补充一个关于 ShutdownHook 的示例，通过这种方式可以优雅的停止线程：

```java
public class ShutdownHookThreadDemo {
    public static void main(String[] args) throws IOException {
        GenericApplicationContext context = new GenericApplicationContext();
        context.addApplicationListener(new ApplicationListener<ContextClosedEvent>() {
            @Override
            public void onApplicationEvent(ContextClosedEvent event) {
                System.out.printf("[线程 %s] ContextClosedEvent 处理\n", Thread.currentThread().getName());
            }
        });
        context.refresh();
        context.registerShutdownHook();
        System.out.println("按任意键继续并且关闭Spring 应用上下文");
        System.in.read();
        context.close();
    }
}
```

## 面试题

### Spring 应用上下文生命周期有哪些阶段？

可以简单的回答为：

- 刷新阶段 - ConfigurableApplicationContext#refresh()
- 启动阶段 - ConfigurableApplicationContext#start()
- 停止阶段 - ConfigurableApplicationContext#stop()
- 关闭阶段 - ConfigurableApplicationContext#close()

### Environment 完整的生命周期？

主要分为 refresh()方法之前和 refresh()方法之后，在 refresh()方法之前可以主动填充自定义的 Environment 对象，在 refresh()方法之后会创建默认的 Environment 对象。

# Spring 总结

## Spring 核心特性

![image-20210628202410655](https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210628202410655.png)

## Spring 核心价值

![image-20210628202440062](https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210628202440062.png)

# 附录

## 为什么说 ObjectFactory 提供的是延迟依赖查找？

原因：

- ObjectFactory（或 ObjectProvider）可关联某一类型 Bean
- ObjectFactory（或 ObjectProvider）对象在被依赖注入和依赖查询时并未实时查找关联类型 Bean
- ObjectFactory（或 ObjectProvider）调用 getObject()方法时，目标 Bean 才被依赖查找

总结：ObjectFactory（或 ObjectProvider）相当于某一类型 Bean 依赖查找代理对象。

这里我们可以编写一个示例：

```java
public class ObjectFactoryLazyLookupDemo {
    public static void main(String[] args) {
        AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext();
        context.register(ObjectFactoryLazyLookupDemo.class);
        context.refresh();

        ObjectFactoryLazyLookupDemo demo = context.getBean(ObjectFactoryLazyLookupDemo.class);
        // 代理对象
        ObjectProvider<User> objectProvider = demo.objectProvider;
        ObjectFactory<User> userObjectFactory = demo.userObjectFactory;

        // ObjectFactory和ObjectProvider
        System.out.println("userObjectFactory == objectProvider: " +
                (userObjectFactory == objectProvider));
        // 结果为true，说明两者的底层实现是一样的。
        System.out.println("userObjectFactory.getClass() == objectProvider.getClass(): " +
                (userObjectFactory.getClass() == objectProvider.getClass()));

        // 实际对象(延迟查找)
        System.out.println(userObjectFactory.getObject());
        System.out.println(objectProvider.getObject());
        System.out.println(context.getBean(User.class));
        context.close();
    }

    @Autowired
    private ObjectFactory<User> userObjectFactory;

    @Autowired
    private ObjectProvider<User> objectProvider;

    @Bean
    @Lazy
    public User user() {
        User user = new User();
        user.setId("111111");
        user.setName("胡先森");
        return user;
    }
}
```

也可以在 DefaultListableBeanFactory.DependencyObjectProvider 中看到相关的原理，只有在调用 getObject 的时候，才会根据泛型的具体化进行依赖查找，创建对象，而不是直接去查找，也就是所谓的延迟依赖查找。

<img src="https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210629102005648.png" alt="image-20210629102005648" style="zoom:50%;" />

## 依赖查找（注入）的 Bean 会被缓存嘛？

- 单例 Bean（Singleton）- 会
  - 缓存位置：org.springframework.beans.factory.support.DefaultSingletonBeanRegistry#singletonObjects 属性
- 原型 Bean（Prototype）- 不会
  - 当依赖查询或依赖注入时，根据 BeanDefinition 每次创建
- 其他 Scope Bean
  - request：每个 ServletRequest 内部缓存，生命周期维持在每次 HTTP 请求
  - session：每个 HttpSeesion 内部缓存，生命周期维持在每个用户 HTTP 会话
  - application：当前 Servlet 应用内部缓存

相关的示例代码：

```java
public class BeanCachingDemo {
    public static void main(String[] args) {
        AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext();
        context.register(BeanCachingDemo.class);
        context.refresh();

        BeanCachingDemo beanCachingDemo = context.getBean(BeanCachingDemo.class);

        for (int i = 0; i < 9; i++) {
            // singletonBean会被缓存
            System.out.println(beanCachingDemo == context.getBean(BeanCachingDemo.class));
        }
        User user = context.getBean(User.class);

        for (int i = 0; i < 9; i++) {
            // prototype不会被缓存
            System.out.println(user == context.getBean(User.class));
        }
        context.close();
    }

    @Bean
    @Scope("prototype")
    public static User user() {
        User user = new User();
        user.setId("111111");
        user.setName("胡先森");
        return user;
    }
}
```

其中单例对象的最为复杂，在 DefaultSingletonBeanRegistry#getSingleton 中可以看到核心的逻辑：

<img src="https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210629104114854.png" style="zoom: 50%;" />

在每次进行依赖查找（注入）的时候不是直接创建对象，而是会现在缓存的字段 singletonObjects 中进行获取。

原型作用域的 Bean 每次在依赖查找（注入）的时候都会根据 BeanDefinition 重新构建 Bean。

总而言之，只有 Prototype 的 Bean 不会进行缓存，其他情况下均会进行缓存。Prototype 的 Bean 在被容器创建之后就会与容器脱钩，不再有生命周期等特性。

## @Bean 的处理流程是怎样的？

- 解析范围 - Configuration Class 中的@Bean 方法
- 方法类型 - 静态@Bean 方法和实例@Bean 方法

在找到标注了@Configuration Class 的类之后，会获取到所有的@Bean 的方法，根据标注的@Bean 的方法解析出相应的 BeanDefinition，然后创建对象，相关的逻辑在

ConfigurationClassBeanDefinitionReader#loadBeanDefinitionsForBeanMethod 方法中，另外在解析静态方法和实例方法的时候，有一些差别：

<img src="https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210629112032376.png" alt="image-20210629112032376" style="zoom:50%;" />

可以看到，如果是实例方法，那么首先要获取到实例方法所在的类的实例，静态方法的初始化会更早。

## BeanFactory 是如何处理循环依赖的？

预备知识：

- 循环依赖开关（方法）- AbstractAutowireCapableBeanFactory#setAllowCircularReferences
- 单例工程（属性）- DefaultSingletonBeanRegistry#singletonFactories
- 获取早期未处理 Bean（方法） - AbstractAutowireCapableBeanFactory#getEarlyBeanReference
- 早期未处理 Bean（属性） - DefaultSingletonBeanRegistry#earlySingletonObjects

循环依赖的示例，首先定义一个学生类：

```java
public class Student {

    private Long id;

    private String name;

    @Autowired
    private ClassRoom classRoom;

    public Long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public ClassRoom getClassRoom() {
        return classRoom;
    }

    public void setClassRoom(ClassRoom classRoom) {
        this.classRoom = classRoom;
    }

    @Override
    public String toString() {
        return "Student{" +
                "id=" + id +
                ", name='" + name + '\'' +
                ", classRoom.name=" + classRoom.getName() +
                '}';
    }
}
```

然后定义一个教室类：

```java
public class ClassRoom {

    private String name;

    @Autowired
    private Collection<Student> students;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public Collection<Student> getStudents() {
        return students;
    }

    public void setStudents(Collection<Student> students) {
        this.students = students;
    }

    @Override
    public String toString() {
        return "ClassRoom{" +
                "name='" + name + '\'' +
                ", students=" + students +
                '}';
    }
}
```

测试示例：

```java
public class CircularReferencesDemo {

    public static void main(String[] args) {
        AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext();
        // 注册 Configuration Class
        context.register(CircularReferencesDemo.class);

        // 如果设置为 false，则抛出异常信息如：currently in creation: Is there an unresolvable circular reference?
        // 默认值为 true
        context.setAllowCircularReferences(true);

        // 启动 Spring 应用上下文
        context.refresh();

        System.out.println("Student : " + context.getBean(Student.class));
        System.out.println("ClassRoom : " + context.getBean(ClassRoom.class));

        // 关闭 Spring 应用上下文
        context.close();
    }

    @Bean
    public static Student student() {
        Student student = new Student();
        student.setId(1L);
        student.setName("张三");
        return student;
    }

    @Bean
    public static ClassRoom classRoom() {
        ClassRoom classRoom = new ClassRoom();
        classRoom.setName("C122");
        return classRoom;
    }
}
```

处理循环依赖的核心代码：

<img src="https://blog-1304855543.cos.ap-guangzhou.myqcloud.com/blog/img/image-20210629152452981.png" alt="image-20210629152452981" style="zoom:50%;" />
