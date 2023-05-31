# WEB-HW-08
First Part
Create an Atlas MongoDB cloud database.

Use the Mongoengine ODM to create models for storing data from these files in the "authors" and "quotes" collections.

When storing quotes, the author field in the document should not be a string value but a ReferenceField field that stores the ObjectID from the "authors" collection.

Write scripts to load JSON files into the cloud database.

Implement a script to search for quotes by tag, author name, or a set of tags. The script runs in an infinite loop and accepts commands via the standard input using the following format: command:value.


Second Part
Write two scripts: consumer.py and producer.py. Use RabbitMQ to simulate email distribution to contacts using queues.

Using ODM Mongoengine, create a contact model. The model must include fields for full name, email, and a boolean field that defaults to False. This field indicates whether the message has been sent to the contact and should be set to True when it is sent. You can come up with the other fields for payload yourself.

When the producer.py script is executed, it generates a specific number of fake contacts and stores them in the database. It then puts a message into the RabbitMQ queue that contains the ObjectID of the created contact, and does this for all generated contacts.

The consumer.py script receives a message from the RabbitMQ queue, processes it, and simulates sending the message via email using a dummy function. After sending the message, the logical field for the contact should be set to True. The script runs continuously, waiting for incoming messages from RabbitMQ.
