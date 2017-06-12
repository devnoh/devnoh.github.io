*Simple Usage of Spring Retry*

1. pom.xml
```
<dependency>
    <groupId>org.springframework.retry</groupId>
    <artifactId>spring-retry</artifactId>
</dependency>
```
2. Spring Configuration

```
@EnableRetry
```

3. Usage with @Retryable Annotation (Method Level)

```
// Try 3 times (2 times after first try) with interval 5 seconds.

@Retryable(value = {Exception.class}, maxAttempts = 3, backoff = @Backoff(delay = 5000))
public List<VehicleData> getVehicleInventoryByDealer(String dealerCode) throws IccClientException {
	// do something
}
```

4. Usage with RetryTemplate (Code Block Level)
```
private RetryTemplate retryTemplate() {
    SimpleRetryPolicy retryPolicy = new SimpleRetryPolicy();
    retryPolicy.setMaxAttempts(3);

    FixedBackOffPolicy backOffPolicy = new FixedBackOffPolicy();
    backOffPolicy.setBackOffPeriod(3000); // 3 seconds

    RetryTemplate template = new RetryTemplate();
    template.setRetryPolicy(retryPolicy);
    template.setBackOffPolicy(backOffPolicy);
    return template;
}

// Try 3 times (2 times after first try) with interval 3 seconds.

retryTemplate().execute(context -> {
	// do something
});
```
