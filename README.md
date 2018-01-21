### Install Kafka

- for linux user follow installation instruction from [here](https://www.tutorialspoint.com/apache_kafka/apache_kafka_installation_steps.htm)
- By default Kafka runs on port `9092`

-otherwise for vagrant setup click [here](https://github.com/chandankuiry/apache-kafka-setup/tree/master/vagrant-file) 
-If you install kafka using vagrant then Kafka server will be listening on `192.168.33.10` port `9092`.

### Project requirements:
 - python 3
 - Kafka [installed]((https://www.tutorialspoint.com/apache_kafka/apache_kafka_installation_steps.htm))
 - [Virtualenv](https://virtualenv.pypa.io/en/stable/).
 - pip installed


#### setting up :
clone this repo:
*  ` $ git clone git@github.com:chandankuiry/kafka-stream-project.git`

Create a virtualenv and activate it inside your project directory:
* `$ virtualenv env && source env/bin/activate`

Install required dependencies
* `pip install kafka-python opencv-python Flask`


##Running the program

You will need two terminal to run the application

In the first terminal run consumer.py. open a terminal and type:

`(env)$ python producer.py`



In the second terminal run producer.py and pass in a message "hello"

`(env)$ python consumer.py



Open your browser and navigate to `http://0.0.0.0:5000`


## project


1. When the browser is refreshed the video does not restart .Kafka uses message offset to know how far in the log the consumer had read.
2. If you close the browser while the video is playing the next time you reopen the browser the video picks from where you left it.
3. The producer does not need to be running for  the video to play. Kafka stores the message and avails when the consumer is ready to recieve the message.
4. When both  Producer and Consumer are running the video is recieved almost in real time.
5. The video are processed in a sequential FIFO(first in first out) manner.
6. One message can be shared amongst many Consumers. This reduces the number of request thats would have been made to the producer if it were an API.