# microservice-supporting-env
A group of common services that supporting the micro-services


## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

What things you need to install the software and how to install them

1. JAVA JDK
2. Intellij
3. Maven


### Installing

A step by step series of examples that tell you have to get a development env running

TODO:

### Running the project

1. Checkout the project into your local machine
2. Run config-server service
   - Check is the config server working by open the URL http://localhost:8001/application/default. You should be able to see a Json format data
3. Run discovery-server
   - Run the script on commandline /run-all.sh which will run 3 instances of Eureka
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
