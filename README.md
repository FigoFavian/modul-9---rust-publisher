Questions:

### a. How much data does the publisher program send in one run?

When the publisher gets executed, it will throw five separate messages to the broker before exiting. The main function constructs and publishes five UserCreatedEventMessage instances in a loop, so each run generates exactly five events pushed into the queue.

### b. What does it mean that both publisher and subscriber use amqp://guest:guest@localhost:5672?
That URI is the connection string for your AMQP broker and breaks down as follows:

a. Protocol (amqp://) specifies you’re speaking the AMQP protocol.
b. Credentials (guest:guest) the username and password pair used to authenticate.
c. Host (localhost) points at the local machine (127.0.0.1).
d. Port (5672) the default port RabbitMQ listens on for AMQP traffic.

By configuring both publisher and subscriber are both connected in the same RabbitMQ instance locally on port 5672 and using the same login. This lets messages from your publisher end up in the queue for subscriber.