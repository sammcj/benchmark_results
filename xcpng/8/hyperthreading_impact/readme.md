# Hyperthreading Impact on XCP-ng 8 (Beta 1)

It has been suggested by Intel to consider disabling Hyperthreading due to bugs in their CPU designs when running sensitive workloads.

<!-- MarkdownTOC -->

- [Test conditions:](#test-conditions)
    - [Host](#host)
    - [VMs](#vms)
- [Test 1 - Phoronix Test Suite - pybench and openssl](#test-1---phoronix-test-suite---pybench-and-openssl)
- [Test 2 - Sysbench Multithreaded Prime Benchmark](#test-2---sysbench-multithreaded-prime-benchmark)
- [Results](#results)

<!-- /MarkdownTOC -->

<a id="test-conditions"></a>
## Test conditions:

<a id="host"></a>
### Host

- HPE BL460c Gen9 (Latest Firmware as of 28/05/2019)
- 2x Xeon E5-2690 v4, 256GB DDR4 ECC
- 2x Crucial MX500 250GB SSDs HPE Smartarry RAID1
- XCP-ng 8 (Beta 1), Xen 4.11
- No VMs online or activity occuring other than those being tested

<a id="vms"></a>
### VMs

- 2x identical VMs, each provisioned with 28 vCPUs
- CentOS 7 (latest updates installed)
- Kernel 5.1.5-1 (elrepo)
- 28 vCPU
- phoronix-test-suite 8.8.0

<a id="test-1---phoronix-test-suite---pybench-and-openssl"></a>
## [Test 1 - Phoronix Test Suite - pybench and openssl](test_1_phoronix_pybench_openssl.md)

- First test: Single VM, HT on
- Second test: Two VMs, HT on (run at the same time using `tmux-cssh -sc vm1 vm2`)
- Third test: Single VM, HT off
- Fourth Test: Two VMs, HT off (run at the same time using `tmux-cssh -sc vm1 vm2`)

<a id="test-2---sysbench-multithreaded-prime-benchmark"></a>
## [Test 2 - Sysbench Multithreaded Prime Benchmark](hyperthreading_impact/test_2_sysbench_prime.md)

- First test: Single VM, HT on
- Second test: Two VMs, HT on (run at the same time using `tmux-cssh -sc vm1 vm2`)
- Third test: Single VM, HT off
- Fourth Test: Two VMs, HT off (run at the same time using `tmux-cssh -sc vm1 vm2`)

<a id="results"></a>
# Results

- **Significant performance decrease (38.7725%) when running multithreaded Sysbench CPU benchmarks on multiple VM when hyperthreading is disabled.**
- No significant performance decrease when running Phoronix Test Suite's Pybench and OpenSSL benchmarks in parallel across two VMs when hyperthreading is disabled.