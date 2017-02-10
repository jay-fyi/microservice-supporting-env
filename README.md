# microservice-supporting-env
A group of common services that supporting the micro-services


## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

What things you need to install the software and how to install them

1. JAVA JDK
2. Intellij
3. Maven
4. Rabbit MQ


### Installing

A step by step series of examples that tell you have to get a development env running

TODO:

### Running the project the first time

1. Checkout the project into your local machine
2. Run a Rabbit MQ Broker (This is used by the Config Server and all service clients, which using the Spring Cloud Bus to dynamically update config data)
    - Download [Rabbit MQ](https://www.rabbitmq.com/download.html).
    - Run Rabbit MQ
       ```
       e.g. >sudo rabbitmq-server start
       ```
    - Check is the MQ running
       ```
       e.g. >sudo rabbitmqctl status
       ```
3. (OPTIONAL) Enable [Rabbit MQ Management Plugin](https://www.rabbitmq.com/management.html)
    - Enable the plugin
      ```
       e.g. >sudo rabbitmq-plugins enable rabbitmq_management
       ```
    - Check is the Management Plugin working by open the URL http://localhost:15672/
      - default username: guest
      - default password: guest
4. Run config-server service. More details about [Spring Cloud Config Server](https://cloud.spring.io/spring-cloud-config/spring-cloud-config.html)
   - Either run on Intellj directly or using Maven or executable jar
        - Using Maven
        ```
        e.g. {PROJECT_DIR}/config-server/>mvn spring-boot:run
        ```
        - Using executable jar - deploy to your target directory
        ```
        e.g. >java -jar {PROJECT_DIR}/target/config-server-{VERSION}.jar
        ```

   - Check is the config server working by open the URL http://localhost:8001/application/default. You should be able to see a Json format data
5. Run discovery-server
   - Run the script in command-line /run-all.sh which will run 3 instances of Eureka
   - Check is the Eureka working by open the URL http://localhost:8011/. You should be able to see a Spring Eureka page with system status
 

## Running the tests

Explain how to run the automated tests for this system

N/A

## Built With

* [Spring-boot](https://projects.spring.io/spring-boot/) - The spring framework
* [Maven](https://maven.apache.org/) - Dependency Management

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/jay-fyi/microservice-supporting-env/tags).

## Authors

* **Jason Yu** - *Initial work* - [Jay-fyi](https://github.com/jay-fyi)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone who's code was used
* Inspiration
* etc
