# Key Value Store

A Key-Value Store is a flexible NoSQL database that's often used for caching an dynamic configuration. Popular options include DynamoDB, Etcd, Redis, and ZooKeeper.



### Technologies

#### Redis

An **in-memory** key-value store. Does offer some persistent storage options but is typically used as a really fast, best-effort caching solution. Redis is also often used to implement rate limiting.

#### ZooKeeper

ZooKeeper is a strongly consistent, highly available key-value store. It's often used to store important configurations or to perform leader elections.

#### Etcd

Etcd is a strongly consistent and highly available key-value store that's often used to implement leader election in a system.
