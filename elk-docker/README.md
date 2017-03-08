# Log Management with ELK
A group of common services that supporting the micro-services


## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

What things you need to install the software and how to install them

1. Docker


### Installing

A step by step series of examples that tell you have to get a development env running

TODO:

### Running the project the first time
1. Install [Docker](https://www.docker.com/)
2. Run the ELK Stack with Docker [ELK Docker](https://elk-docker.readthedocs.io/#installation).
    - Pull the ELK docker image
     ```
     >sudo docker pull sebp/elk
     ```
    - Run the container from the image 
     ```
     >sudo docker run -p 5601:5601 -p 9200:9200 -p 5044:5044 -it --name elk sebp/elk
     ```
    - Next time, you can just start the container 
     ```
     >sudo docker start elk
     ```
3. Install [FileBeat](https://www.elastic.co/products/beats/filebeat) - logs shipper.
4. Config FileBeat to send logs to ElasticSearch - [Forwarding logs](https://elk-docker.readthedocs.io/#forwarding-logs) 
    - Copy the config and template file
     ```
     >sudo mkdir -p /etc/filebeat/
     >sudo cp ./nginx-filebeat/filebeat.yml /etc/filebeat/filebeat.yml
     >sudo cp {HOME_FileBeat}/filebeat.template.json /etc/filebeat/filebeat.template.json
     ```
    - Copy the CA cert (NOTE: this is a generic cert for testing purpose)
     ```
     >sudo mkdir -p /etc/pki/tls/certs
     >sudo cp ./nginx-filebeat/logstash-beats.crt /etc/pki/tls/certs/logstash-beats.crt
     ```
5. Create filebeat index template in Elasticsearch
     ```
     >curl -XPUT 'http://localhost:9200/_template/filebeat?pretty' -d@/etc/filebeat/filebeat.template.json
     ```
6. Run fileBeat 
     ```
     >cd {HOME_FileBeat}/bin
     >sudo ./filebeat -e -c /etc/filebeat/filebeat.yml -d "publish"
     ```     


 

## Running the tests

Explain how to run the automated tests for this system

N/A

## Built With
 

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/jay-fyi/microservice-supporting-env/tags).

## Authors

* **Jason Yu** - *Initial work* - [Jay-fyi](https://github.com/jay-fyi)

See also the list of [contributors](https://github.com/jay-fyi/microservice-supporting-env/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone who's code was used
* Inspiration
* etc
