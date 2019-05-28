# Test 2 - Sysbench Multithreaded Prime Benchmarks

<!-- MarkdownTOC -->

- [Results](#results)
- [Test Command](#test-command)
  - [First test: Single VM, HT on](#first-test-single-vm-ht-on)
  - [Second test: Two VMs, HT on](#second-test-two-vms-ht-on)
  - [Third test: Single VM, HT off](#third-test-single-vm-ht-off)
  - [Fourth Test: Two VMs, HT off](#fourth-test-two-vms-ht-off)
- [Performance Impact of Disabling Hyperthreading](#performance-impact-of-disabling-hyperthreading)

<!-- /MarkdownTOC -->

<a id="results"></a>
# Results

- **Significant performance decrease (38.7725%) when running multithreaded Sysbench CPU benchmarks in parallel on two VMs when hyperthreading is disabled.**

<a id="test-command"></a>
# Test Command

- `sysbench --test=cpu --threads=28 --cpu-max-prime=99999`

<a id="first-test-single-vm-ht-on"></a>
## First test: Single VM, HT on

```
# sysbench --test=cpu --threads=28 --cpu-max-prime=99999 run
WARNING: the --test option is deprecated. You can pass a script name or path on the command line without any options.
sysbench 1.0.17 (using system LuaJIT 2.0.4)

Running the test with following options:
Number of threads: 28
Initializing random number generator from current time


Prime numbers limit: 99999

Initializing worker threads...

Threads started!

CPU speed:
    events per second:  1082.77

General statistics:
    total time:                          10.0245s
    total number of events:              10856

Latency (ms):
         min:                                   23.13
         avg:                                   25.82
         max:                                   93.23
         95th percentile:                       32.53
         sum:                               280306.00

Threads fairness:
    events (avg/stddev):           387.7143/36.12
    execution time (avg/stddev):   10.0109/0.01
```

<a id="second-test-two-vms-ht-on"></a>
## Second test: Two VMs, HT on

```
# sysbench --test=cpu --threads=28 --cpu-max-prime=99999 run
WARNING: the --test option is deprecated. You can pass a script name or path on the command line without any options.
sysbench 1.0.17 (using system LuaJIT 2.0.4)

Running the test with following options:
Number of threads: 28
Initializing random number generator from current time


Prime numbers limit: 99999

Initializing worker threads...

Threads started!

CPU speed:
    events per second:   856.62

General statistics:
    total time:                          10.0295s
    total number of events:              8593

Latency (ms):
         min:                                   26.84
         avg:                                   32.64
         max:                                   97.81
         95th percentile:                       38.94
         sum:                               280488.25

Threads fairness:
    events (avg/stddev):           306.8929/0.77
    execution time (avg/stddev):   10.0174/0.01
```

```
# sysbench --test=cpu --threads=28 --cpu-max-prime=99999 run
WARNING: the --test option is deprecated. You can pass a script name or path on the command line without any options.
sysbench 1.0.17 (using system LuaJIT 2.0.4)

Running the test with following options:
Number of threads: 28
Initializing random number generator from current time


Prime numbers limit: 99999

Initializing worker threads...

Threads started!

CPU speed:
    events per second:   856.74

General statistics:
    total time:                          10.0291s
    total number of events:              8594

Latency (ms):
         min:                                   23.59
         avg:                                   32.62
         max:                                   94.81
         95th percentile:                       38.94
         sum:                               280358.31

Threads fairness:
    events (avg/stddev):           306.9286/0.84
    execution time (avg/stddev):   10.0128/0.01
```

- Total combined events per second: **1713.36**

<a id="third-test-single-vm-ht-off"></a>
## Third test: Single VM, HT off

```
# sysbench --test=cpu --threads=28 --cpu-max-prime=99999 run
WARNING: the --test option is deprecated. You can pass a script name or path on the command line without any options.
sysbench 1.0.17 (using system LuaJIT 2.0.4)

Running the test with following options:
Number of threads: 28
Initializing random number generator from current time


Prime numbers limit: 99999

Initializing worker threads...

Threads started!

CPU speed:
    events per second:  1140.17

General statistics:
    total time:                          10.0223s
    total number of events:              11429

Latency (ms):
         min:                                   22.81
         avg:                                   24.52
         max:                                  130.07
         95th percentile:                       29.19
         sum:                               280283.25

Threads fairness:
    events (avg/stddev):           408.1786/1.39
    execution time (avg/stddev):   10.0101/0.01
```

<a id="fourth-test-two-vms-ht-off"></a>
## Fourth Test: Two VMs, HT off

```
# sysbench --test=cpu --threads=28 --cpu-max-prime=99999 run
WARNING: the --test option is deprecated. You can pass a script name or path on the command line without any options.
sysbench 1.0.17 (using system LuaJIT 2.0.4)

Running the test with following options:
Number of threads: 28
Initializing random number generator from current time


Prime numbers limit: 99999

Initializing worker threads...

Threads started!

CPU speed:
    events per second:   577.53

General statistics:
    total time:                          10.0290s
    total number of events:              5793

Latency (ms):
         min:                                   23.22
         avg:                                   48.36
         max:                                  171.24
         95th percentile:                      102.97
         sum:                               280146.65

Threads fairness:
    events (avg/stddev):           206.8929/1.21
    execution time (avg/stddev):   10.0052/0.02
```

```
# sysbench --test=cpu --threads=28 --cpu-max-prime=99999 run
WARNING: the --test option is deprecated. You can pass a script name or path on the command line without any options.
sysbench 1.0.17 (using system LuaJIT 2.0.4)

Running the test with following options:
Number of threads: 28
Initializing random number generator from current time


Prime numbers limit: 99999

Initializing worker threads...

Threads started!

CPU speed:
    events per second:   579.39

General statistics:
    total time:                          10.0346s
    total number of events:              5815

Latency (ms):
         min:                                   23.04
         avg:                                   48.00
         max:                                  160.31
         95th percentile:                      102.97
         sum:                               279148.80

Threads fairness:
    events (avg/stddev):           207.6786/1.10
    execution time (avg/stddev):   9.9696/0.04
```

- Total combined events per second: **1156.92**

---

<a id="performance-impact-of-disabling-hyperthreading"></a>
# Performance Impact of Disabling Hyperthreading

- 38.7725% difference

