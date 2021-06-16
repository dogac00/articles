
This is article is about running .NET TestContainers in GitHub Actions but I will first briefly mention TestContainers.

# What is a TestContainer

TestContainer is nothing but a Docker container that you run in your tests. They are providing us throwaway docker container instances to test our business.

# What is the need for TestContainers?

Early on, we ran our integration tests in multiple different environments.

For example, we ran our tests using in-memory databases.
In memory databases actually quite useful, lightweight and fast but what if we want to run Kafka or RabbitMQ or other technology 
that does not provide a in-memory library. In these cases, we ran our data-access layer and eventing integration tests in our development environments.
This is quite easy to do and required no setup in tests code side. However, the drawback is other applications or other tests can use the development
machines too. Or we have to clean our development machines at intervals.

# This is a test class

``` cs
public class Person {
  public long Id { get; set; }
  public string Name { get; set; }
}
```
