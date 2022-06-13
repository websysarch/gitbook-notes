# Caching

* Write through cache
* Write Back cache



### Write through cache

The request would overwrite the cache first and then the database both in the same request.



### Write Back Cache

The request will just update the cache. and at later time, it would be synced to the database.

### Problems to take care:

* If the data is immutable
* Staleness of data
* Invalidation of stale data
* Partitioning of data
* Eviction of data

### Terms

#### Cache

A piece of hardware or software that stores data, typically meant to retrieve that data faster than otherwise.

Cache can become stale if the main source of truth for the data gets updated and the cache doesn't/

#### Cache Hit

When requested data is found in a cache

#### Cache Miss

When requested data could not been found in a cache

#### Cache Eviction Policy

The policy by which values get evicted or removed from a cache. Popular cache eviction policies include **LRU** (least recently used), **FIFO** (First in first out), and **LFU** (Least frequently used)

#### CDN (Content Delivery Network)

A CDN is a third party service that acts like a cache for all your servers.
