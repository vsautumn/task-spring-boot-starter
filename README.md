# task-spring-boot-starter
a distributed task module

## version 0.1.0
Supporting distributed services, find the first service registered to Eureka as master, and then the master performs timing tasks.

use example as follows:

step1:
```
@SpringBootApplication
@EnableDiscoveryClient
@EnableDistributedTask
@EnableScheduling
    public static void main(String[] args) {
        SpringApplication.run(Application.class, args);
    }
}
```
step2:
```
@Component
public class MySchedule {
    @OneTask
    @Scheduled(fixedRate = 5000)
    public void exec() {
        System.out.println("just run in single server.");
    }
}
```

