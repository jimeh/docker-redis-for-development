# Redis for Development

When using redis locally for development, you typically want to use the default
redis.conf file which periodically backs up data to disk. The official
[Redis](https://hub.docker.com/_/redis/) images does not load a config, so a
restart means a complete wipe of all data in redis.

This image uses the default
[redis.conf](https://raw.githubusercontent.com/antirez/redis/3.2.0/redis.conf)
and makes it Docker friendly via the following changes:

- Bind to `0.0.0.0` instead of `127.0.0.1`.
- Set `protected-mode` to `no` instead of `yes`.
- Disable use of PID file.

## Running

```
docker run -d -p 6379 jimeh/redis-for-development
```

