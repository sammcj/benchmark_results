# Test 2 - Phoronix Pybench and OpenSSL Multithreaded Benchmarks

<!-- MarkdownTOC -->

- [Results](#results)
- [Test Command](#test-command)
    - [Phoronix Test Suite VM Information Output](#phoronix-test-suite-vm-information-output)
    - [First test: Single VM, HT on](#first-test-single-vm-ht-on)
    - [Second test: Two VMs, HT on](#second-test-two-vms-ht-on)
        - [Combined Performance Results](#combined-performance-results)
    - [Third test: Single VM, HT off](#third-test-single-vm-ht-off)
    - [Fourth Test: Two VMs, HT off](#fourth-test-two-vms-ht-off)
        - [Combined Performance Results](#combined-performance-results-1)

<!-- /MarkdownTOC -->

<a id="results"></a>
# Results

- No significant performance decrease when running Phoronix Test Suite's Pybench and OpenSSL benchmarks in parallel on two VMs when hyperthreading is disabled.

<a id="test-command"></a>
# Test Command

- `phoronix-test-suite run pybench openssl`

<a id="phoronix-test-suite-vm-information-output"></a>
## Phoronix Test Suite VM Information Output

Note: Phoronix incorrectly detects the host CPU cores as 32, the E5-2690 v4 CPU has 28 cores!

```
Phoronix Test Suite v8.8.0
System Information


  PROCESSOR:          2 x Intel Xeon E5-2690 v4
    Core Count:       32
    Thread Count:     28
    Extensions:       SSE 4.2 + AVX2 + AVX + RDRAND + FSGSBASE
    Cache Size:       35840 KB
    Microcode:        0xb000036

  GRAPHICS:           DRM emulated
    Screen:           1024x768

  MOTHERBOARD:        Xen HVM domU
    BIOS Version:     4.11.1-7.3.xcpng8.0
    Chipset:          Intel 440FX 82441FX PMC

  MEMORY:             16384 MB + 16376 MB RAM

  DISK:               10GB
    File-System:      ext4
    Mount Options:    noatime rw seclabel

  OPERATING SYSTEM:   CentOS Linux 7
    Kernel:           5.1.5-1.el7.elrepo.x86_64 (x86_64)
    Compiler:         GCC 4.8.5 20150623
    System Layer:     Xen HVM domU 4.11.1-7.3.xcpng8.0
    Security:         SELinux
                      + KPTI
                      + __user pointer sanitization
                      + Full generic retpoline IBPB: conditional IBRS_FW STIBP: disabled RSB filling
                      + SSB disabled via prctl and seccomp
                      + PTE Inversion
```

<a id="first-test-single-vm-ht-on"></a>
## First test: Single VM, HT on

```
phoronix-test-suite run pybench openssl HT on single vm:

    Processor: 2 x Intel Xeon E5-2690 v4 (32 Cores), Motherboard: Xen HVM domU (4.11.1-7.3.xcpng8.0 BIOS), Chipset: Intel 440FX 82441FX PMC, Memory: 16384 MB + 16376 MB RAM, Disk: 10GB, Graphics: DRM emulated

    OS: CentOS Linux 7, Kernel: 5.1.5-1.el7.elrepo.x86_64 (x86_64), Compiler: GCC 4.8.5 20150623, File-System: ext4, Screen Resolution: 1024x768, System Layer: Xen HVM domU 4.11.1-7.3.xcpng8.0


    OpenSSL 1.1.1
    RSA 4096-bit Performance
    Signs Per Second > Higher Is Better
    phoronix-test-suite run pybench openssl HT on single vm . 5801|===================================================================================================================================================================================================================================================================================================================================


    PyBench 2018-02-16
    Total For Average Test Times
    Milliseconds < Lower Is Better
    phoronix-test-suite run pybench openssl HT on single vm . 1736|===================================================================================================================================================================================================================================================================================================================================
```

- Results Uploaded To: https://openbenchmarking.org/result/1905289-HV-PHORONIXT30

<a id="second-test-two-vms-ht-on"></a>
## Second test: Two VMs, HT on

```
phoronix-test-suite run pybench openssl HT on:

        Processor: 2 x Intel Xeon E5-2690 v4 (32 Cores), Motherboard: Xen HVM domU (4.11.1-7.3.xcpng8.0 BIOS), Chipset: Intel 440FX 82441FX PMC, Memory: 16384 MB + 16376 MB RAM, Disk: 10GB, Graphics: DRM emulated

        OS: CentOS Linux 7, Kernel: 5.1.5-1.el7.elrepo.x86_64 (x86_64), Compiler: GCC 4.8.5 20150623, File-System: ext4, Screen Resolution: 1024x768, System Layer: Xen HVM domU 4.11.1-7.3.xcpng8.0


    OpenSSL 1.1.1
    RSA 4096-bit Performance
    Signs Per Second > Higher Is Better
    phoronix-test-suite run pybench openssl HT on . 3018|=============================================================================================================================================================================================================================================================================================================================================


    PyBench 2018-02-16
    Total For Average Test Times
    Milliseconds < Lower Is Better
    phoronix-test-suite run pybench openssl HT on . 1753|=============================================================================================================================================================================================================================================================================================================================================
```

- Results Uploaded To: https://openbenchmarking.org/result/1905284-HV-PHORONIXT50

```
phoronix-test-suite run pybench openssl HT on:

        Processor: 2 x Intel Xeon E5-2690 v4 (32 Cores), Motherboard: Xen HVM domU (4.11.1-7.3.xcpng8.0 BIOS), Chipset: Intel 440FX 82441FX PMC, Memory: 16384 MB + 16376 MB RAM, Disk: 10GB, Graphics: DRM emulated

        OS: CentOS Linux 7, Kernel: 5.1.5-1.el7.elrepo.x86_64 (x86_64), Compiler: GCC 4.8.5 20150623, File-System: ext4, Screen Resolution: 1024x768, System Layer: Xen HVM domU 4.11.1-7.3.xcpng8.0


    OpenSSL 1.1.1
    RSA 4096-bit Performance
    Signs Per Second > Higher Is Better
    phoronix-test-suite run pybench openssl HT on . 3025|=============================================================================================================================================================================================================================================================================================================================================


    PyBench 2018-02-16
    Total For Average Test Times
    Milliseconds < Lower Is Better
    phoronix-test-suite run pybench openssl HT on . 1751|=============================================================================================================================================================================================================================================================================================================================================
```

- Results Uploaded To: https://openbenchmarking.org/result/1905289-HV-PHORONIXT50

<a id="combined-performance-results"></a>
### Combined Performance Results

- Total combined RSA 4096-bit Performance (Higher is better): **6043**
- Total combined PyBench 2018-02-16 (Lower is better): **3504**


<a id="third-test-single-vm-ht-off"></a>
## Third test: Single VM, HT off

```
phoronix-test-suite run pybench openssl HT off single vm:

    Processor: 2 x Intel Xeon E5-2690 v4 (32 Cores), Motherboard: Xen HVM domU (4.11.1-7.3.xcpng8.0 BIOS), Chipset: Intel 440FX 82441FX PMC, Memory: 16384 MB + 16376 MB RAM, Disk: 10GB, Graphics: DRM emulated

    OS: CentOS Linux 7, Kernel: 5.1.5-1.el7.elrepo.x86_64 (x86_64), Compiler: GCC 4.8.5 20150623, File-System: ext4, Screen Resolution: 1024x768, System Layer: Xen HVM domU 4.11.1-7.3.xcpng8.0


    OpenSSL 1.1.1
    RSA 4096-bit Performance
    Signs Per Second > Higher Is Better
    phoronix-test-suite run pybench openssl HT off single vm . 5926|==========================================================================================================================================================================================================================================================================================================================================


    PyBench 2018-02-16
    Total For Average Test Times
    Milliseconds < Lower Is Better
    phoronix-test-suite run pybench openssl HT off single vm . 1732|==========================================================================================================================================================================================================================================================================================================================================
```

- Results Uploaded To: https://openbenchmarking.org/result/1905285-HV-PHORONIXT33

<a id="fourth-test-two-vms-ht-off"></a>
## Fourth Test: Two VMs, HT off

```
phoronix-test-suite run pybench openssl HT off:

        Processor: 2 x Intel Xeon E5-2690 v4 (32 Cores), Motherboard: Xen HVM domU (4.11.1-7.3.xcpng8.0 BIOS), Chipset: Intel 440FX 82441FX PMC, Memory: 16384 MB + 16376 MB RAM, Disk: 10GB, Graphics: DRM emulated

        OS: CentOS Linux 7, Kernel: 5.1.5-1.el7.elrepo.x86_64 (x86_64), Compiler: GCC 4.8.5 20150623, File-System: ext4, Screen Resolution: 1024x768, System Layer: Xen HVM domU 4.11.1-7.3.xcpng8.0


    OpenSSL 1.1.1
    RSA 4096-bit Performance
    Signs Per Second > Higher Is Better
    phoronix-test-suite run pybench openssl HT off . 3024|====================================================================================================================================================================================================================================================================================================================================================


    PyBench 2018-02-16
    Total For Average Test Times
    Milliseconds < Lower Is Better
    phoronix-test-suite run pybench openssl HT off . 1755|====================================================================================================================================================================================================================================================================================================================================================
```

- Results Uploaded To: https://openbenchmarking.org/result/1905284-HV-PHORONIXT80

```
phoronix-test-suite run pybench openssl HT off:

        Processor: 2 x Intel Xeon E5-2690 v4 (32 Cores), Motherboard: Xen HVM domU (4.11.1-7.3.xcpng8.0 BIOS), Chipset: Intel 440FX 82441FX PMC, Memory: 16384 MB + 16376 MB RAM, Disk: 10GB, Graphics: DRM emulated

        OS: CentOS Linux 7, Kernel: 5.1.5-1.el7.elrepo.x86_64 (x86_64), Compiler: GCC 4.8.5 20150623, File-System: ext4, Screen Resolution: 1024x768, System Layer: Xen HVM domU 4.11.1-7.3.xcpng8.0


    OpenSSL 1.1.1
    RSA 4096-bit Performance
    Signs Per Second > Higher Is Better
    phoronix-test-suite run pybench openssl HT off . 3002|====================================================================================================================================================================================================================================================================================================================================================


    PyBench 2018-02-16
    Total For Average Test Times
    Milliseconds < Lower Is Better
    phoronix-test-suite run pybench openssl HT off . 1740|====================================================================================================================================================================================================================================================================================================================================================
```

- Results Uploaded To: https://openbenchmarking.org/result/1905288-HV-PHORONIXT80

<a id="combined-performance-results-1"></a>
### Combined Performance Results

- Total combined RSA 4096-bit Performance (Higher is better): **6026**
- Total combined PyBench 2018-02-16 (Lower is better): **3495**