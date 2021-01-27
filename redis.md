# Basics

- Redis stands for REmote DIctionary Server. It's a NoSQL key-value data store utilizing ky-value pairs, often for caching purposes.

# Data Types

- A Redis key is a binary-safe String, with a maximum size of 512MB.

- Unlike `localStorage`, Redis keys can contain strings, hashes, lists (specifically linked lists), sets, sorted sets, etc.

- Lists should be preferred as keys when the strengths of linked lists apply, such as order of insertion and write speed. 

- Sets are similar to lists, but don't allow duplicates. Their strength as keys lie in constant time for adding and removing operations, and when uniqueness of data storage matters.

- Sorted sets are for when we need our elements to be sorted.

- The Hash value is a field-value type.

# Commands

## Strings

- Set a record: `SET guitar 450`. The can be performed multiple times to overwrite values.
- Get a record: `GET guitar`
- Set a time-to-live for retrieval commands, in seconds: `SETEX 120 450 guitar`. First argument is the time to set, second is the value.
- Set a time-to-live for retrieval commands, in milliseconds: `PSETEX 120000 450 guitar`. 
- The above is also writeable as `SET key value PX milliseconds`
- `SETNX`: Checks for a key, but doesn't immediately write the value if the key isn't present.
- `STRLEN`: Checks for the length of the value for a particular key
- Set multiple records in a single command: `MSET banana 32 apple 45`
- `MGET`: get multiple records in a single command.
- `KEYS`: tells us which keys are currently stored in Redis
- `INCR`: increments the given key's value by 1
- `INCRBY`: like INCR, but you can specify a value to increment by
- `INCRBYFLOAT`: ...and again, but by a floating point number
- `DECR`: decrement by 1
- `DECRBY`: decrement by a specified amount
- `DEL`: deletes one or more specified keys
- `FLUSHALL`: flush all keys in Redis
- `APPEND`: append a given string to a value

## Lists

- The head is on the "left-hand" side of the list, and the tail on the "right-hand" side.

- `LPUSH`: Insert a value at the head of the list
- `LRANGE`: See what values are present for a given key
- `LPOP`: Remove the value at the head of the list
- `RPUSH`: Insert a value at the tail of the list.
- `RPOP`: Remove the value at the tail of the list
- `LLEN`: Find the length of the list
- `LINDEX`: Find the element at the given index in the list
- `LSET`: Update the value at the given index in the list
- `LPUSHX`: Add a value at the head of the list, if that list exists
- `LINSERT`: Insert a value before a specified element in the list

## Sets

- `SADD`: Add an element to a set
- `SMEMBERS`: See all members of a set
- `SISMEMBER`: Check to see if an element is a member of a set
- `SCARD`: Get a count of members present in a set
- `SDIFF`: Find the difference between two sets
- `SUNION`: Finds the union of two or more sets
- `SREM`: Remove specified members from the set
- `SPOP`: Remove a random value from the set
- `SMOVE`: Move a value from one set to another
  

## Sorted Sets

- `ZADD`: Add elements to a sorted set
- `ZRANGE`: Fetch all elements for a particular key
- `ZRANGEBYSCORE`: Fetch elements in a particular range of scores
- `ZCARD`: Get the number of elements in the sorted set
- `ZCOUNT`: Find the number of elements within a certain range of scores
- `ZREM`: Remove a member from a sorted set
- `ZRANK`: Find the index of an element in a sorted set
- `ZREVRANK`: Find the rank from the reverse.
- `ZSCORE`: Get the rank of an element
  
## Hashes

- `HMSET`: Store a hash in Redis
- `HGETALL`: Get all field-value pairs for a given key.
- `HGET`: Find the value of a particular field within a key
- `HEXISTS`: Check to see if a particular field exists in the database or not
- `HDEL`: Delete a field from a hash
- `HSETNX`: Checks for a field, but doesn't immediately write the value if the field isn't present.


