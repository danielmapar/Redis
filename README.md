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