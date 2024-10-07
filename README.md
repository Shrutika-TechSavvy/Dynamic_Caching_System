# Dynamic_Caching_System
Objective: Design and implement a dynamic multilevel caching system that efficiently manages data across multiple cache levels. The system should support dynamic addition of cache levels, eviction policies, and data retrieval across these levels.
This project implements a flexible, multi-level cache system in Java. It supports dynamic addition and removal of cache levels, each with configurable size and eviction policies (LRU or LFU). The system is designed to be thread-safe and efficient for concurrent access.

**Features**

1. Multiple cache levels with configurable sizes.
2. Support for LRU (Least Recently Used) and LFU (Least Frequently Used) eviction policies.
3. Dynamic addition and removal of cache levels.
4. Thread-safe operations using read-write locks.
5. Automatic data promotion to higher cache levels on access.


**Structure**

The project consists of the following main classes:

1. DynamicCacheSystem: The main class that manages multiple cache levels.
2. CacheLevel: Represents a single level of cache with a specific size and eviction policy.
3. EvictionPolicy: An interface for implementing different eviction policies.
4. LRUPolicy: Implementation of the Least Recently Used (LRU) eviction policy.
5. LFUPolicy: Implementation of the Least Frequently Used (LFU) eviction policy.

**Thread Safety**
1. The DynamicCacheSystem uses ReadWriteLock to ensure thread-safe operations.
2. Multiple threads can read from the cache concurrently.
3.Write operations (such as adding or removing cache levels) are exclusive.

**Performance Considerations**
1. The system automatically promotes frequently accessed data to higher cache levels, improving access times for hot data.
2. The LFU policy performs better in scenarios with stable access patterns.
3. The LRU policy is optimal for recency-based access patterns.
Adding or removing cache levels is an expensive operation and should be done sparingly.

**Future Improvements**
1. Implement size-aware eviction to handle variable-sized cache entries.
2. Add support for time-based expiration of cache entries.
