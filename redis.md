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
- `STRLEN` checks for the length of the value for a particular key
- Set multiple records in a single command: `MSET banana 32 apple 45`
- `MGET` get multiple records in a single command.
