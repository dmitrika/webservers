# webservers
wrk test for different webservers
wrk --latency -t12 -c100 -d10s http://localhost:3000/

## Benchmark setup

Benchmarks were performed on the following hardware:
```
  Model Name:	MacBook Pro
  Processor Name:	Intel Core i7
  Processor Speed:	2,2 GHz
  Total Number of Cores:	4
  L2 Cache (per Core):	256 KB
  L3 Cache:	6 MB
  Memory:	16 GB
```

## Rocket – Rust (nightly) web framework

```
Running 10s test @ http://localhost:8000/
  12 threads and 100 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     4.06ms   29.95ms   1.38s    98.28%
    Req/Sec     1.60k     0.98k    3.80k    62.33%
  Latency Distribution
     50%    2.17ms
     75%    2.46ms
     90%    3.80ms
     99%   35.23ms
  47839 requests in 10.10s, 6.66MB read
Requests/sec:   4735.06
Transfer/sec:    675.12KB
```

## Iron – An Extensible, Concurrent Web Framework for Rust
```
Running 10s test @ http://localhost:3000/
  12 threads and 100 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     1.05ms    3.69ms 151.70ms   99.83%
    Req/Sec     7.44k     2.67k    9.99k    78.17%
  Latency Distribution
     50%    0.87ms
     75%    0.97ms
     90%    1.06ms
     99%    1.13ms
  671477 requests in 10.10s, 73.00MB read
Requests/sec:  66480.29
Transfer/sec:      7.23MB
```

## Echo – High performance, minimalist Go web framework
```
Running 10s test @ http://localhost:1323/
  12 threads and 100 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     1.46ms  251.03us   8.15ms   81.22%
    Req/Sec     5.47k   829.62    20.13k    98.75%
  Latency Distribution
     50%    1.41ms
     75%    1.63ms
     90%    1.73ms
     99%    2.13ms
  655279 requests in 10.10s, 81.24MB read
Requests/sec:  64883.20
Transfer/sec:      8.04MB
```
