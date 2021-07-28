## kafka 
A distributed event streaming platform that lets you read, write, store, and process events
(also called records or messages in the documentation) across many machines

#### Use cases of Kafka 
Messaging
Metrics and logging
Commit log
Stream processing

### Components

Messages are batched rather than being sent individually to reduce overhead -> tradeoff between latency and throughput
Messages batched together are compressed for efficient data transfer

Topic - Messages get written and read from topics. (like folder)

Partition 

A topic has subdivisions known as partitions.
Messages are ordered by time only within a partition and not across the entire topic.
Messages are read from beginning to end in a partition.
Message can only be appended to the end of a partition
Partitions allow Kafka to scale horizontally

Message key 
We can control which partition a message lands in with the use of message keys. like %count

offset - The offset is an integer value that is ever increasing and determines the order of the message within a partition

A single Kafka server is called a broker
Within a cluster, a single broker owns a partition and is said to be the leader. 
All the other partition-replicating brokers are called followers. 

## Producer

```js
KafkaProducer
ProducerRecord future = producer.send(record);
RecordMetadata recordMetadata = future.get();
// We perform a get() on the future object, which turns the send call synchronous

or

producer.send(record, new ProducerCallback());


recordMetadata.offset(), .partition()

producer.flush();
producer.close();
```

`retries` - parameter sets the number of times a producer retries sending a message before giving up and declaring a failure to the client.

A small batch.size means the producer will be sending smaller messages at a higher frequency, which adds more overhead

To improve throughput (at the expense of increasing latency) Kafka can be configured with linger.ms milliseconds to wait for additional messages to be assigned to a batch before sending the batch out.

max.request.size 


### Order gurantee in batch process - 
max.in.flight.requests.per.connection should be set to 1, though it will severely impact the throughput of the producer.


### ACKS acknowledged 
For producers, correctly configuring the acks parameter 
When acks=0 the producer doesn’t wait for an acknowledgement from the broker.
When acks=1 the producer waits to receive an acknowledgement from the leader 
When acks=all the producers receive an acknowledgement when all in-sync replicas have replicated the message(min.insync.replica = 2,3..)


## Consumer

#### poll_loop - 
  poll for new messages and process them in a perpetual loop

```js
KafkaConsumer
consumer.subscribe(Pattern.compile("datajek-.*"));
consumer.poll(oneSecond)
consumer.close();
```

### configuration

The broker will wait for messages to pile up until they are larger in aggregate size than fetch.min.bytes before sending them to the consumer

the offsets are committed automatically, but this behavior can be changed by setting `enable.auto.commit` to false

max.poll.records maximum number of records returned by the poll() call

The configuration max.partition.fetch.bytes specifies the maximum number of bytes returned by a broker per partition

client.id acts as an identifier for a consumer.


poll() don't stop else broker initiates rebalance thinking consumer is dead
so call pause() process message and then resume()

a single consumer to read all the messages in a topic, we’ll need to assign a unique `group.id` to this consumer.
```
// blocking call to commit offset
cosnsumer.commitSync() or commitASync(Handler)
consumer.commitAsync(currentOffsets, null);

consumer.close();
consumer.wakeup();
```

#### types -
>Consumers Equal Number of Partitions
> Single Consumer:
> Partitions in a topic are greater than the number of consumers in a group
