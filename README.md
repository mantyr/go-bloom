# Bloom filter

[![GoDoc](https://godoc.org/github.com/kristinn/go-bloom?status.svg)](https://godoc.org/github.com/kristinn/go-bloom)

Golang bloom filter library with support for both bitset and redis backends.

## Tests and benchmarks

It's easy to run the tests and benchmarks.

```bash
make test
```

This will try to connect to Redis listening on the default port (6379) running on localhost.

You can supply the environment variable `REDIS_HOST` in case you are not running redis on localhost.

```bash
REDIS_HOST=192.168.33.10 make test
```

### Benchmarking

Benchmarking results on my Macbook Pro Mid 2014 (2.5 ghz Intel Core i7, 16 GB RAM, with "flash" drive (SSD?)), running redis locally with no special configuration.

```
BenchmarkRedisQueueAppend-8	 2000000	       957 ns/op
BenchmarkRedisSave-8       	  200000	      9550 ns/op
BenchmarkRedisExists-8     	   50000	     29933 ns/op
BenchmarkBitsetAppend-8    	 2000000	       932 ns/op
BenchmarkBitsetSave-8      	 2000000	       906 ns/op
BenchmarkBitsetExists-8    	 2000000	       647 ns/op
```
