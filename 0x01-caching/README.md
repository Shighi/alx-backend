# Caching Project

This project implements different caching algorithms as part of the ALX Backend curriculum. It explores various caching replacement policies including FIFO, LIFO, LRU, MRU, and LFU.

## Background Context

In this project, we learn about caching systems and their importance in optimizing application performance. Caches store frequently accessed data to improve retrieval times and reduce load on primary data sources.

## Requirements

* All files interpreted/compiled on Ubuntu 18.04 LTS using Python 3.7
* All files should end with a new line
* First line of all files should be exactly `#!/usr/bin/env python3`
* Code should use pycodestyle style (version 2.5)
* All files must be executable
* All modules, classes, and functions require proper documentation
* Documentation should be meaningful sentences explaining the purpose

## Base Class

All cache classes in this project inherit from the `BaseCaching` class which provides:
- A MAX_ITEMS constant (set to 4)
- A cache_data dictionary to store all items
- Basic methods that must be implemented by child classes

## Files and Implementations

1. **0-basic_cache.py**: Implements a basic dictionary cache with no size limit
   - Class: `BasicCache`
   - No eviction policy needed

2. **1-fifo_cache.py**: First-In-First-Out caching system
   - Class: `FIFOCache`
   - Eviction: Removes the first item put in cache when limit is reached

3. **2-lifo_cache.py**: Last-In-First-Out caching system
   - Class: `LIFOCache`
   - Eviction: Removes the last item put in cache when limit is reached

4. **3-lru_cache.py**: Least Recently Used caching system
   - Class: `LRUCache`
   - Eviction: Removes the least recently used item when limit is reached

5. **4-mru_cache.py**: Most Recently Used caching system
   - Class: `MRUCache`
   - Eviction: Removes the most recently used item when limit is reached

6. **100-lfu_cache.py**: Least Frequently Used caching system (Advanced)
   - Class: `LFUCache`
   - Eviction: Removes the least frequently used item when limit is reached
   - Uses LRU as a tiebreaker when multiple items have the same usage frequency

## Usage Examples

Each file includes a main program demonstrating how to use the cache. To test:

```bash
$ ./0-main.py  # Test basic cache
$ ./1-main.py  # Test FIFO cache
# etc.
```

## Learning Objectives

Through this project, you will learn:
- What a caching system is
- What FIFO, LIFO, LRU, MRU, and LFU mean
- What the purpose of a caching system is
- What limits a caching system can have

## Author
SHIGHI
