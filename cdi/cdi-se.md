# Java SE support

The Java SE support in weld is now standardized, it is useful when you want to get CDI support out of Java EE application servers.

Given a simple CDI bean.

```java
@Named
@ApplicationScoped
public class Greeter {

    public void say(String name) {
        System.out.println("Hi, " + name);
    }
}
```

You can start CDI `SeContainer` like this.

```java
 SeContainerInitializer initializer = SeContainerInitializer.newInstance();
try (SeContainer container = initializer.initialize()) {
    assertTrue(container.isRunning());
    Set<Bean<?>> greeters = container.getBeanManager().getBeans("greeter");
    assertTrue(greeters.size() == 1);
}
```

There is a `try-resources` statement, `SeContainer` is a `AutoClosable` and can be closed automatically at the end.

To bootstrap CDI container for Java SE, you have to add the following dependencies in project.

```markup
<dependency>
    <groupId>org.jboss.weld.se</groupId>
    <artifactId>weld-se-shaded</artifactId>
    <version>3.0.0.Final</version>
</dependency>
```

Weld also provides some simple APIs to bootstrap a CDI container.

```java
Weld weld = new Weld();

try (WeldContainer container = weld.initialize()) {
    Greeter greeter = container.select(Greeter.class).get();
    assertTrue(greeter != null);
}
```

You can utilize Weld APIs to modify beans in the CDI container lifecycle.

```java
@Test(expected = UnsatisfiedResolutionException.class)
public void bootWeldSeContainer() {
    Extension testExtension = ContainerLifecycleObserver.extensionBuilder()
        .add(afterBeanDiscovery((e) -> System.out.println("Bean discovery completed!")))
        .add(processAnnotatedType().notify((e) -> {
            if (e.getAnnotatedType().getJavaClass().getName().startsWith("com.hantsylab")) {
                e.veto();
            }
        }))
        .build();
    try (WeldContainer container = new Weld().addExtension(testExtension).initialize()) {
        Greeter greeter = container.select(Greeter.class).get();
        //assertTrue(greeter == null);
    }
}
```

In the above codes, it vetoes `Greeter` bean in `processAnnotatedType` phase, the later bean select operation will cause an exception `UnsatisfiedResolutionException` thrown.

Grab the [source codes](https://github.com/hantsy/ee8-sandbox) from my GitHub account, and have a try.

