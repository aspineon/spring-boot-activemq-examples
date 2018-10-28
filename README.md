<b>Spring-boot-activemq (jms spring boot application in memory) </b>:

A simple application that sends a message to a queue of an in-memory instance of ActiveMQ and subscribes it with a @jmslistener annotated method of a managed bean.

Spring Boot has a in-memory ActiveMQ instance ( similar to in-memory H2 database). I configure a queue from the in-memory ActiveMQ: in Config.java. The queue name is “inmemory.queue” but can be named anything.

Producer.java – I create a Producer that will allow the message to be sent to the queue:The producer class is a Rest controller. I injected the JmsTemplate class used to send messages through its method convertAndSend( ), and injected the queue defined earlier. The message is a String passed as parameter of a Rest endpoint method, sending it through HTTP GET.

I access the message through a Consumer inside the same project: Consumer.java

@JmsListener listen for anything inside the “inmemory.queue” and the listener() method will retrieve what’s in the queue (the message).In the browser at http://localhost:8081/publish/hello%20world%! I got the results below: "published sucessfuly" and in console: "Received Message->hello world"

<b>Spring  boot activemq standaone application </b>
A simple application that sends a message to a queue of stanone instance of ActiveMQ and subscribes it with a @jmslistener annotated method of a managed bean.
