# [Spring]([https://www.soapui.org/](https://spring.io/))

## JPA

### Debug if the execution is in the transaction

<sup>04-01-2023, source: self</sup>

```java
// org.springframework.transaction.support.TransactionSynchronizationManager

TransactionSynchronizationManager.isActualTransactionActive();
```

### Debug transactions

<sup>09-12-2022, source: [Medium](https://medium.com/@aleksanderkolata/use-case-02-spring-transactional-requires-new-propagation-mode-cb7c16e1dd16)</sup>

```properties
log4j.logger.org.springframework.orm.jpa=TRACE
log4j.logger.org.springframework.transaction.interceptor=TRACE
```
```properties
logging.level.org.springframework.orm.jpa=TRACE
logging.level.org.springframework.transaction.interceptor=TRACE
```

### Get Spring bean programatically

<sup>04-01-2023, source: self</sup>

```java
// org.springframework.web.context.ContextLoader

ContextLoader.getCurrentWebApplicationContext().getBean("myBean", MyBean.class);
```
