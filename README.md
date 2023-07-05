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

## Section 11: Organizing Data with Sorted Sets

* ![sorted_set](./images/sorted_set_1.png)

* ![sorted_set](./images/sorted_set_2.png)

* ![sorted_set](./images/sorted_set_3.png)

* ![sorted_set](./images/sorted_set_4.png)

* ![sorted_set](./images/sorted_set_5.png)

* ![sorted_set](./images/sorted_set_6.png)

* ![sorted_set](./images/sorted_set_7.png)

* ![sorted_set](./images/sorted_set_8.png)

* ![sorted_set](./images/sorted_set_9.png)

* ![sorted_set](./images/sorted_set_10.png)

* ![sorted_set](./images/sorted_set_11.png)

* ![sorted_set](./images/sorted_set_12.png)

* ![sorted_set](./images/sorted_set_13.png)

* ![sorted_set](./images/sorted_set_14.png)

* ![sorted_set](./images/sorted_set_15.png)

* ![sorted_set](./images/sorted_set_16.png)

* ![sorted_set](./images/sorted_set_17.png)

* ![sorted_set](./images/sorted_set_18.png)

* ![sorted_set](./images/sorted_set_19.png)

* ![sorted_set](./images/sorted_set_20.png)

* ![sorted_set](./images/sorted_set_21.png)
    * `REV` reverts the sorted set from `ASC` to `DSC`.

## Section 13: From Relational Data to Redis

* ![sort](./images/sort_1.png)
    * `SORT` is a great way to `JOIN` data. You can first get a set of `keys` from a `set` and the use that to search for other `keys`.
        * e.g. `books:*->year`. The `*` is used to look for other keys.

* ![sort](./images/sort_2.png)

* ![sort](./images/sort_3.png)

* ![sort](./images/sort_4.png)

* ![sort](./images/sort_5.png)

* ![sort](./images/sort_6.png)

* ![sort](./images/sort_7.png)

* ![sort](./images/sort_8.png)

* ![sort](./images/sort_9.png)

* ![sort](./images/sort_10.png)

* ![sort](./images/sort_11.png)

* ![sort](./images/sort_12.png)

## Section 14: HyeperLogLog Structures

* ![hyperloglog](./images/hyperloglog_1.png)

* ![hyperloglog](./images/hyperloglog_2.png)

* ![hyperloglog](./images/hyperloglog_3.png)

* ![hyperloglog](./images/hyperloglog_4.png)

* ![hyperloglog](./images/hyperloglog_5.png)

* ![hyperloglog](./images/hyperloglog_6.png)

* ![hyperloglog](./images/hyperloglog_7.png)


## Section 15: Storing Collections with Lists

* ![list](./images/list_1.png)

* ![list](./images/list_2.png)

* ![list](./images/list_3.png)

* ![list](./images/list_4.png)

* ![list](./images/list_5.png)

* ![list](./images/list_6.png)

* ![list](./images/list_7.png)

* ![list](./images/list_8.png)

* ![list](./images/list_9.png)

* ![list](./images/list_10.png)

* ![list](./images/list_11.png)

* ![list](./images/list_12.png)

* ![list](./images/list_13.png)

* ![list](./images/list_14.png)

* ![list](./images/list_15.png)

* ![list](./images/list_16.png)

* ![list](./images/list_17.png)

* ![list](./images/list_18.png)

* ![list](./images/list_19.png)

* ![list](./images/list_20.png)

* ![list](./images/list_21.png)

* ![list](./images/list_22.png)

## Section 16: Transactions

* ![concurrency](./images/concurrency_1.png)

* ![concurrency](./images/concurrency_2.png)

* ![concurrency](./images/concurrency_3.png)

* ![concurrency](./images/concurrency_4.png)
    * `MULTI` is used for a transaction containing many commands.

* ![concurrency](./images/concurrency_5.png)
    * As soon as `WATCH` is called on a `key`, it will watch for changes on that `key`. If any change happens, and we try to do a `MULTI` with a set of commands, as soon as we call `EXEC` the transaction will fail.
    * All the commands in a transaction are serialized and executed sequentially. **A request sent by another client will never be served in the middle of the execution of a Redis Transaction.** This guarantees that the commands are executed as a single isolated operation.
    * `WATCH` helps us to `GET` values and evalute if changes happened.

* ![concurrency](./images/concurrency_6.png)

## Section 17: Extending Redis with Scripting

* ![lua](./images/lua_1.png)

* ![lua](./images/lua_2.png)

* ![lua](./images/lua_3.png)

* ![lua](./images/lua_4.png)

* ![lua](./images/lua_5.png)

* ![lua](./images/lua_6.png)

* ![lua](./images/lua_7.png)

* ![lua](./images/lua_8.png)

* ![lua](./images/lua_9.png)

* ![lua](./images/lua_10.png)
    * The advantage of Lua script is that we can execute custom redis operations on Redis not available in the redis commands arsenal & redis does not allow any operation until script is executed end to end.

* ![lua](./images/lua_11.png)

* ![lua](./images/lua_12.png)

* ![lua](./images/lua_13.png)

## Section 18: Understanding and Solving Concurrency Issues

* ![concurrency_issue](./images/concurrency_issue_1.png)

* ![concurrency_issue](./images/concurrency_issue_2.png)
    * We could "RETRY" this operation many times to circumvent issues with `WATCH` failing on some transactions.

* ![concurrency_issue](./images/concurrency_issue_3.png)
    * In this example we spin 3 processes and we track how many transactions fail using `WATCH`. No retries in this case.

* ![concurrency_issue](./images/concurrency_issue_4.png)

* ![concurrency_issue](./images/concurrency_issue_5.png)

* ![concurrency_issue](./images/concurrency_issue_6.png)

* ![concurrency_issue](./images/concurrency_issue_7.png)

* ![concurrency_issue](./images/concurrency_issue_8.png)

* ![concurrency_issue](./images/concurrency_issue_9.png)

* ![concurrency_issue](./images/concurrency_issue_10.png)

* ![concurrency_issue](./images/concurrency_issue_11.png)

* ![concurrency_issue](./images/concurrency_issue_12.png)

* ![concurrency_issue](./images/concurrency_issue_13.png)

* ```js
    import { createClient, defineScript } from 'redis';
    import { itemsKey, itemsByViewsKey, itemsViewsKey } from '$services/keys';

    const client = createClient({
        socket: {
            host: process.env.REDIS_HOST,
            port: parseInt(process.env.REDIS_PORT)
        },
        password: process.env.REDIS_PW,
        scripts: {
            // This is the script registered
            unlock: defineScript({
                NUMBER_OF_KEYS: 1,
                transformArguments(key: string, token: string) {
                    return [key, token];
                },
                transformReply(reply: any) {
                    return reply;
                },
                SCRIPT: `
                    if redis.call('GET', KEYS[1]) == ARGV[1] then
                        return redis.call('DEL', KEYS[1])
                    end
                `
            })
        }
    );

    client.on('error', (err) => console.error(err));
    client.connect();

    export { client };
    ```

* ```js
    import { client } from './client';
    import { randomBytes } from 'crypto';

    export const withLock = async (key: string, cb: (signal: any) => any) => {
        // Initialize a few variables to control retry behavior
        const retryDelayMs = 100;
        let retries = 20;

        // Generate a random value to store at the lock key
        const token = randomBytes(6).toString('hex');
        // Create the lock key
        const lockKey = `lock:${key}`;

        // Set up a while loop to implement the retry behavior
        while (retries >= 0) {
            retries--;
            // Try to do a SET NX operation
            const acquired = await client.set(lockKey, token, {
                NX: true,
                PX: 2000
            });

            if (!acquired) {
                // ELSE brief pause (retryDelayMs) and then retry
                await pause(retryDelayMs);
                continue;
            }

            // IF the set is successful, then run the callback
            try {
                const signal = { expired: false };
                setTimeout(() => {
                    signal.expired = true;
                }, timeoutMs);

                const proxiedClient = buildClientProxy(timeoutMs);
                const result = await cb(proxiedClient, signal);
                return result;
            } finally {
                await client.unlock(lockKey, token);
            }
        }
    };

    type Client = typeof client;
    const buildClientProxy = (timeoutMs: number) => {
        const startTime = Date.now();

        const handler = {
            get(target: Client, prop: keyof Client) {
                if (Date.now() >= startTime + timeoutMs) {
                    throw new Error('Lock has expired.');
                }

                const value = target[prop];
                return typeof value === 'function' ? value.bind(target) : value;
            }
        };
        // The Proxy object enables you to create a proxy for another object, which can intercept and redefine fundamental operations for that object.
	    return new Proxy(client, handler) as Client;
    };

    const pause = (duration: number) => {
        return new Promise((resolve) => {
            setTimeout(resolve, duration);
        });
    };
    ```

* ```js
    import type { CreatSubAttrs, Bid } from '$services/types';
    import { bidHistoryKey, itemsKey, itemsByPriceKey } from '$services/keys';
    import { client, withLock } from '$services/redis';
    import { DateTime } from 'luxon';
    import { getItem } from './items';

    const pause = (duration: number) => {
        return new Promise((resolve) => {
            setTimeout(resolve, duration);
        });
    };

    // The following is the callback that is acting as client to make use of the acquired lock

    export const createSubs = async (attrs: CreateSubsAttrs) => {
        return withLock(attrs.itemId, async (lockedClient: typeof client, signal: any) => {
            // 1) Fetching the item
            // 2) Doing validation
            // 3) Writing some data
            const item = await getItem(attrs.itemId);

            if (!item) {
                throw new Error('Item does not exist');
            }
            if (item.price >= attrs.amount) {
                throw new Error('Bid too low');
            }
            if (item.endingAt.diff(DateTime.now()).toMillis() < 0) {
                throw new Error('Item closed to bidding');
            }

            const serialized = serializeHistory(attrs.amount, attrs.createdAt.toMillis());

            if (signal.expired) {
                throw new Error('Lock expired, cant write any more data');
            }

            return Promise.all([
                lockedClient.rPush(bidHistoryKey(attrs.itemId), serialized),
                lockedClient.hSet(itemsKey(item.id), {
                    bids: item.bids + 1,
                    price: attrs.amount,
                    highestBidUserId: attrs.userId
                }),
                lockedClient.zAdd(itemsByPriceKey(), {
                    value: item.id,
                    score: attrs.amount
                })
            ]);
	    });


        const serializeHistory = (amount: number, createdAt: number) => {
            return `${amount}:${createdAt}`;
        };

        const deserializeHistory = (stored: string) => {
            const [amount, createdAt] = stored.split(':');

            return {
                amount: parseFloat(amount),
                createdAt: DateTime.fromMillis(parseInt(createdAt))
            };
        };
    };
    ```

## Section 19: Querying Data with RediSearch

* ![redisearch](./images/redisearch_1.png)

* ![redisearch](./images/redisearch_2.png)

* ![redisearch](./images/redisearch_3.png)
    * Get raw source code of module, compile it, load the module using `MODULE LOAD` on Redis.

* ![redisearch](./images/redisearch_4.png)
    * An alternative copy of Redis containing additional modules.

* ![redisearch](./images/redisearch_5.png)

* ![redisearch](./images/redisearch_6.png)

* ![redisearch](./images/redisearch_7.png)

* ![redisearch](./images/redisearch_8.png)

* ![redisearch](./images/redisearch_9.png)
    * Instead using Redis Core and maintaining a sorted set and other structures to do search on a hash map item, we could use Redis Search and create an index to do such query.

* ![redisearch](./images/redisearch_10.png)

* ![redisearch](./images/redisearch_11.png)

* ![redisearch](./images/redisearch_12.png)

* ![redisearch](./images/redisearch_13.png)

* ![redisearch](./images/redisearch_14.png)

* ![redisearch](./images/redisearch_15.png)

* ![redisearch](./images/redisearch_16.png)

* ![redisearch](./images/redisearch_17.png)

* ![redisearch](./images/redisearch_18.png)

* ![redisearch](./images/redisearch_19.png)

* ![redisearch](./images/redisearch_20.png)

* ![redisearch](./images/redisearch_21.png)

* ![redisearch](./images/redisearch_22.png)

* ![redisearch](./images/redisearch_23.png)

* ![redisearch](./images/redisearch_24.png)

* ![redisearch](./images/redisearch_25.png)

## Section 20: Search In Action

* ![redisearch](./images/redisearch_26.png)

* ![redisearch](./images/redisearch_27.png)

* ![redisearch](./images/redisearch_28.png)

* ![redisearch](./images/redisearch_29.png)

* ![redisearch](./images/redisearch_30.png)

* ![redisearch](./images/redisearch_31.png)

* ![redisearch](./images/redisearch_32.png)

* ![redisearch](./images/redisearch_33.png)

* ![redisearch](./images/redisearch_34.png)

* ![redisearch](./images/redisearch_35.png)

* ![redisearch](./images/redisearch_36.png)

* ![redisearch](./images/redisearch_37.png)

* ![redisearch](./images/redisearch_38.png)

* ![redisearch](./images/redisearch_39.png)

* ![redisearch](./images/redisearch_40.png)

* ![redisearch](./images/redisearch_41.png)

* ![redisearch](./images/redisearch_42.png)

* ![redisearch](./images/redisearch_43.png)

* ![redisearch](./images/redisearch_44.png)

* ![redisearch](./images/redisearch_45.png)

* ![redisearch](./images/redisearch_46.png)

* ![redisearch](./images/redisearch_47.png)

* ![redisearch](./images/redisearch_48.png)

* ![redisearch](./images/redisearch_49.png)

* ![redisearch](./images/redisearch_50.png)

* ![redisearch](./images/redisearch_51.png)

* ![redisearch](./images/redisearch_52.png)

* ![redisearch](./images/redisearch_53.png)

* ![redisearch](./images/redisearch_54.png)

* ![redisearch](./images/redisearch_55.png)

* ![redisearch](./images/redisearch_56.png)

* ![redisearch](./images/redisearch_57.png)

* ![redisearch](./images/redisearch_58.png)

* ![redisearch](./images/redisearch_59.png)

* ![redisearch](./images/redisearch_60.png)

* ![redisearch](./images/redisearch_61.png)

* ![redisearch](./images/redisearch_62.png)

* ![redisearch](./images/redisearch_63.png)

* ![redisearch](./images/redisearch_64.png)

* ![redisearch](./images/redisearch_65.png)

* ![redisearch](./images/redisearch_66.png)

* ![redisearch](./images/redisearch_67.png)

* ![redisearch](./images/redisearch_68.png)

* ![redisearch](./images/redisearch_69.png)

* ![redisearch](./images/redisearch_70.png)

* ![redisearch](./images/redisearch_71.png)

* ![redisearch](./images/redisearch_72.png)

* ![redisearch](./images/redisearch_73.png)

* ![redisearch](./images/redisearch_74.png)

## Section 21: Service Communication with Streams

* ![streams](./images/streams_1.png)

* ![streams](./images/streams_2.png)

* ![streams](./images/streams_3.png)

* ![streams](./images/streams_4.png)

* ![streams](./images/streams_5.png)

* ![streams](./images/streams_6.png)

* ![streams](./images/streams_7.png)

* ![streams](./images/streams_8.png)

* ![streams](./images/streams_9.png)

* ![streams](./images/streams_10.png)

* ![streams](./images/streams_11.png)

* ![streams](./images/streams_12.png)

* ![streams](./images/streams_13.png)

* ![streams](./images/streams_14.png)

* ![streams](./images/streams_15.png)

* ![streams](./images/streams_16.png)

* ![streams](./images/streams_17.png)

* ![streams](./images/streams_18.png)

* ![streams](./images/streams_19.png)

* ![streams](./images/streams_20.png)

* ![streams](./images/streams_21.png)

* ![streams](./images/streams_22.png)

* ![streams](./images/streams_23.png)

* ![streams](./images/streams_24.png)

* ![streams](./images/streams_25.png)

* ![streams](./images/streams_26.png)

* ![streams](./images/streams_27.png)

* ![streams](./images/streams_28.png)

* ![streams](./images/streams_29.png)

* ![streams](./images/streams_30.png)

* ![streams](./images/streams_31.png)

* ![streams](./images/streams_32.png)

* ![streams](./images/streams_33.png)

* ![streams](./images/streams_34.png)

* ![streams](./images/streams_35.png)

* ![streams](./images/streams_36.png)

* ![streams](./images/streams_37.png)

* ![streams](./images/streams_38.png)