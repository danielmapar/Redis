# Redis: The Complete Developer's Guide

## Section 2: Commands for Adding and Querying Data

* ```redis
    SET message 'Hi message!'
    GET message
    ```

* ![basic_commands](./images/basic_commands_1.png)

* ![basic_commands](./images/basic_commands_2.png)

* ![basic_commands](./images/basic_commands_3.png)

* ![basic_commands](./images/basic_commands_4.png)

* redis.io/commands

* ![basic_commands](./images/basic_commands_5.png)

* ![basic_commands](./images/basic_commands_6.png)
    * As an example, the `expiration` parameter is super useful when we are caching information a database.

* ![basic_commands](./images/basic_commands_6.png)

* ![basic_commands](./images/basic_commands_7.png)

* ![basic_commands](./images/basic_commands_8.png)

* ![basic_commands](./images/basic_commands_9.png)

* ![basic_commands](./images/basic_commands_10.png)

* ![basic_commands](./images/basic_commands_11.png)

* ![basic_commands](./images/basic_commands_12.png)

* ![basic_commands](./images/basic_commands_13.png)

* ![basic_commands](./images/basic_commands_14.png)

* ![basic_commands](./images/basic_commands_15.png)

* ![basic_commands](./images/basic_commands_16.png)

* ![basic_commands](./images/basic_commands_17.png)

* ![basic_commands](./images/basic_commands_18.png)

* ![basic_commands](./images/basic_commands_19.png)

* ![basic_commands](./images/basic_commands_20.png)

* ![basic_commands](./images/basic_commands_21.png)

* ![basic_commands](./images/basic_commands_22.png)

* ![basic_commands](./images/basic_commands_23.png)

* ![basic_commands](./images/basic_commands_24.png)

* ![basic_commands](./images/basic_commands_25.png)
    * Those commands exist because of race conditions. One example would be two separate servers running the same backend code doing a `GET`, increamenting the value and after that doing a `SET`. At some point those two servers would `GET` the same value and override each others increment operation. This is a typical race condition.

* ![basic_commands](./images/basic_commands_26.png)

## Section 4: Local Redis Setup

* `Redis Stack` contains the core Redis database and some additional modules that extend the functionality of Redis.

* If you do not already have HomeBrew installed, navigate to https://brew.sh/ and run the command at the top in your terminal to install HomeBrew

* At your terminal, run `brew tap redis-stack/redis-stack`

* At your terminal, run `brew install redis-stack`

* To start Redis, run `redis-stack-server`

* To connect to your local Redis server and execute commands, run `redis-cli`

## Hashes in Redis

* ![hash_table](./images/hash_table_1.png)

* ![hash_table](./images/hash_table_2.png)

* ![hash_table](./images/hash_table_3.png)

* ![hash_table](./images/hash_table_4.png)

* ![hash_table](./images/hash_table_5.png)

* ![hash_table](./images/hash_table_6.png)

* ![hash_table](./images/hash_table_7.png)

* ![hash_table](./images/hash_table_8.png)

* ![hash_table](./images/hash_table_9.png)

* ![hash_table](./images/hash_table_10.png)
    * If you try to increment a key that does not exist, it will create it automatically.

* ![hash_table](./images/hash_table_11.png)

* ![hash_table](./images/hash_table_12.png)

## Section 8: Pipelining Commands

* Redis Pipelining
    * A Request/Response server can be implemented so that it is able to process new requests even if the client hasn't already read the old responses. This way it is possible to send multiple commands to the server without waiting for the replies at all, and finally read the replies in a single step.

    * This is called pipelining, and is a technique widely in use for many decades. For instance many POP3 protocol implementations already support this feature, dramatically speeding up the process of downloading new emails from the server.

## Section 9: Enforcing Uniqueness with Sets


* ![set](./images/sets_1.png)

* ![set](./images/sets_2.png)

* ![set](./images/sets_3.png)

* ![set](./images/sets_4.png)

* ![set](./images/sets_5.png)

* ![set](./images/sets_6.png)

* ![set](./images/sets_7.png)

* ![set](./images/sets_8.png)

* ![set](./images/sets_9.png)
    * The first `set` dictates the intersect result.

* ![set](./images/sets_10.png)

* ![set](./images/sets_11.png)

* ![set](./images/sets_12.png)

* ![set](./images/sets_13.png)

* ![set](./images/sets_14.png)

* ![set](./images/sets_15.png)

* ![set](./images/sets_16.png)

* ![set](./images/sets_17.png)