# Reflection
## Questions
*How many data your publisher program will send to the message broker in one run?*
The program will send 5 messages to the message broker, one for each UserCreatedEventMessage.

*The URL `amqp://guest:guest@localhost:5672` is the same as in the subscriber program, what does it mean?*
This URL points to the AMQP server running on the local machine using the default port 5672. Both the publisher and subscriber use this URL, indicating they connect to the same message broker for sending and receiving messages.
## Message Broker with RabbitMQ
### Running RabbitMQ as message broker
<img src="image/image0.png">

### Sending and Processing Event
<img src="image/image1.png">

When a message broker like RabbitMQ is operational, and we run our Subscriber and Publisher programs (using cargo run), the Publisher sends data to the message broker, which is then received by the Subscriber. In the image above, we can see that the Publisher sends data once to the message broker, and the Subscriber receives it.

### Monitoring chart based on publisher
<img src="image/image2.png">

In the image above, I attempted to run the Publisher multiple times, which increased the message rates, and then after a few seconds, I tried running it twice more with a longer interval between runs. From this, I understand that the message rates increase when the Publisher sends data to the message broker. If the message rates are high, the message broker will receive a lot of data from the Publisher.