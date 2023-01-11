# Redis Cluster in Dockerization

### Prerequisites Environment

- Docker
- Port availability from 7000 to 7005

## Build Docker Image

```bash
bash build.sh
```

### start the redis cluster

```bash
bash start.sh
```

### connect to cluster

```
redis-cli -c -p 7000
```

### Stop the cluster

```
docker-compose down
```

### Communicate to Redis Server using redis-cli

redis-cli is a command line tool to communicate with redis-server. To install redis-cli please follow as below.

Complete installation guide is [here](https://redis.io/docs/getting-started/installation/)

Once Redis CLI installed, it can be validated by below.

```bash
redis-cli -h 127.0.0.1 -p 7000
```

#### Basic operation validation with outputs:

```
127.0.0.1:7000> lpush demos redis-macOS-demo
OK
127.0.0.1:7000> rpop demos
"redis-macOS-demo"
```

### Example output in cli

```
○ → redis-cli -c -p 7000 -a myredis
127.0.0.1:7000> set foo bar
-> Redirected to slot [12182] located at 127.0.0.1:7002
OK
127.0.0.1:7002> set hello world
-> Redirected to slot [866] located at 127.0.0.1:7000
OK
127.0.0.1:7000> get foo
-> Redirected to slot [12182] located at 127.0.0.1:7002
"bar"
127.0.0.1:7002> get hello
-> Redirected to slot [866] located at 127.0.0.1:7000
"world"
```