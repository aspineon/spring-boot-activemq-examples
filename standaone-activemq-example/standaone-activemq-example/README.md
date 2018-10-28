JMS STANDAONE ACTIVEMQ EXAMPLE

This example is to illustrate jms messaging with spring boot.
I first  setup a queue for my example. This is done in Spring Java Configuration class .There I configure activemq connection factory
I inject the activemq connection factory.with this factory register the broker uri.
jmstemplatei use to push directly the messages
The producer is publishing some messages and is restcontroller
JmsTemplate makes it very simple to send messages to a JMS destination.