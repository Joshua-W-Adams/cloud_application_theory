# Simple Notification Service (SNS)

Messaging service based on the Pub / Sub messaging pattern. Similar to the MQTT protocol.

Message providers publish messages to SNS TOPIC and multiple consumers can subscribe to these message TOPICS.

Service for when you want multiple consumers of your messages.

Subscribers can be:
- lambda functions
- SQS
- HTTP/HTTPs web servers
- Emails
- SMS messages
- Mobile notifications

SNS can be combined with SQS for message persistance. 

Multiple consumers of a message topic is called the fan out pattern.

## SNS Message filtering

Filtering that can be applied to TOPIC subscriptions.

![](./../../../img/sqs_message_filtering.png)

## SNS First In First Out (FIFO)

Support for enforment of processing messages in order of reciept.
