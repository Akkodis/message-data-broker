# Message Data Broker

## Introduction

Message data broker is a message broker that runs in the MEC server. The current version use ActiveMQ 5.15.11.
This repositoty contains:

- A Message Broker to be deployed in the MEC, which is ActiveMQ (src/)
- An example of sender and receive in python (examples/activemq_clients)

The instruction to build the ActiveMQ source code are available into the REDME in src/ (a Make file with the commands is available).

## Development instructions

Message Broker can be found in src/ folder
* sudo docker-compose up -d
* open http://<ip>:8161
    * manage ActiveMQ broker
    * admin/admin
    * you can see created topics


### Builing the Message DataBroker

To build the activemq source code with docker, creating the image and saving the image.

`make build-image`

If you already saved locally the image, then the image could be loaded:

`make load` 

To clean the loaded image:
`make clean`

Then to run the docker-compose containing the activemq configuration:

`make run` 

and to stop it:

`make stop`


Not required but a command to build and check the docker-compose is provided also:

`make build` 


## Examples 
Have a look at the folder with the examples to run the senders:

- cits_sender_python: a python sender and receiver that run an AMQP sender simulating a number of vehicles that send messages with some properties attached.
    - pip dependencies
    - python-qpid-proton
- image_sender_python: a python sender and receiver that run an AMQP sender simulating a number of vehicle that sends images (different size, but all the same)

Look at the examples README for more details.

- cits_receiver_python: a python example to receive messages from AMQP events


* python3 sender.py -a amqp://user:password@<your_ip>:5673/topic://cits

## Conclusion

#TODO
