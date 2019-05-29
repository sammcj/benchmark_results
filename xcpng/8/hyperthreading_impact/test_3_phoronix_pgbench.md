# Test 3 - Phoronix PGBench Benchmarks

<!-- MarkdownTOC -->

- [Results](#results)
- [Test Command](#test-command)
    - [Phoronix Test Suite VM Information Output](#phoronix-test-suite-vm-information-output)
    - [First test: Single VM, HT on](#first-test-single-vm-ht-on)
    - [Second test: Two VMs, HT on](#second-test-two-vms-ht-on)
    - [Third test: Single VM, HT off](#third-test-single-vm-ht-off)
    - [Fourth Test: Two VMs, HT off](#fourth-test-two-vms-ht-off)
- [Performance Impact of Disabling Hyperthreading](#performance-impact-of-disabling-hyperthreading)

<!-- /MarkdownTOC -->

<a id="results"></a>
# Results

- **WORK IN PROGRESS**

<a id="test-command"></a>
# Test Command

```
# phoronix-test-suite run pgbench

PostgreSQL pgbench 10.3:
    pts/pgbench-1.8.7
    System Test Configuration
        1: Buffer Test
        2: Mostly RAM
        3: On-Disk
        4: Test All Options
        ** Multiple items can be selected, delimit by a comma. **
        Scaling: 2


        1: Single Thread
        2: Normal Load
        3: Heavy Contention
        4: Test All Options
        ** Multiple items can be selected, delimit by a comma. **
        Test: 4


        1: Read Write
        2: Read Only
        3: Test All Options
        ** Multiple items can be selected, delimit by a comma. **
        Mode: 2
```

<a id="phoronix-test-suite-vm-information-output"></a>
## Phoronix Test Suite VM Information Output
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

```

<a id="second-test-two-vms-ht-on"></a>
## Second test: Two VMs, HT on

```
phoronix pgbench 242 HT on:
        Processor: 2 x Intel Xeon E5-2690 v4 (32 Cores), Motherboard: Xen HVM domU (4.11.1-7.3.xcpng8.0 BIOS), Chipset: Intel 440FX 82441FX PMC, Memory: 16384 MB + 16376 MB RAM, Disk: 10GB, Graphics: DRM emulated
        OS: CentOS Linux 7, Kernel: 5.1.5-1.el7.elrepo.x86_64 (x86_64), Compiler: GCC 4.8.5 20150623, File-System: ext4, Screen Resolution: 1024x768, System Layer: Xen HVM domU 4.11.1-7.3.xcpng8.0

    PostgreSQL pgbench 10.3
    Scaling: Mostly RAM - Test: Normal Load - Mode: Read Only
    TPS > Higher Is Better
    phoronix pgbench 242 HT on . 244195|=================================================================================================================================================

    PostgreSQL pgbench 10.3
    Scaling: Mostly RAM - Test: Single Thread - Mode: Read Only
    TPS > Higher Is Better
    phoronix pgbench 242 HT on . 17783|==================================================================================================================================================

    PostgreSQL pgbench 10.3
    Scaling: Mostly RAM - Test: Heavy Contention - Mode: Read Only
    TPS > Higher Is Better
    phoronix pgbench 242 HT on . 328503|=================================================================================================================================================
```

- Results Uploaded To: https://openbenchmarking.org/result/1905298-HV-PHORONIXP44

```
phoronix pgbench 242 HT on:
        Processor: 2 x Intel Xeon E5-2690 v4 (32 Cores), Motherboard: Xen HVM domU (4.11.1-7.3.xcpng8.0 BIOS), Chipset: Intel 440FX 82441FX PMC, Memory: 16384 MB + 16376 MB RAM, Disk: 10GB, Graphics: DRM emulated
        OS: CentOS Linux 7, Kernel: 5.1.5-1.el7.elrepo.x86_64 (x86_64), Compiler: GCC 4.8.5 20150623, File-System: ext4, Screen Resolution: 1024x768, System Layer: Xen HVM domU 4.11.1-7.3.xcpng8.0

    PostgreSQL pgbench 10.3
    Scaling: Mostly RAM - Test: Normal Load - Mode: Read Only
    TPS > Higher Is Better
    phoronix pgbench 242 HT on . 246688|=================================================================================================================================================

    PostgreSQL pgbench 10.3
    Scaling: Mostly RAM - Test: Single Thread - Mode: Read Only
    TPS > Higher Is Better
    phoronix pgbench 242 HT on . 16927|==================================================================================================================================================

    PostgreSQL pgbench 10.3
    Scaling: Mostly RAM - Test: Heavy Contention - Mode: Read Only
    TPS > Higher Is Better
    phoronix pgbench 242 HT on . 331614|=================================================================================================================================================
```

-  Results Uploaded To: https://openbenchmarking.org/result/1905298-HV-PHORONIXP57


- Total combined TPS - Normal Load - Mode: Read Only: **490,883**
- Total combined TPS - Single Thread - Mode: Read Only: **34,710**
- Total combined TPS - Heavy Contention - Mode: Read Only: **660,117**

<a id="third-test-single-vm-ht-off"></a>
## Third test: Single VM, HT off

```
phoronix pgbench 242 HT off single vm:
        Processor: 2 x Intel Xeon E5-2690 v4 (32 Cores), Motherboard: Xen HVM domU (4.11.1-7.3.xcpng8.0 BIOS), Chipset: Intel 440FX 82441FX PMC, Memory: 16384 MB + 16376 MB RAM, Disk: 10GB, Graphics: DRM emulated
        OS: CentOS Linux 7, Kernel: 5.1.5-1.el7.elrepo.x86_64 (x86_64), Compiler: GCC 4.8.5 20150623, File-System: ext4, Screen Resolution: 1024x768, System Layer: Xen HVM domU 4.11.1-7.3.xcpng8.0

    PostgreSQL pgbench 10.3
    Scaling: Mostly RAM - Test: Normal Load - Mode: Read Only
    TPS > Higher Is Better
    phoronix pgbench 242 HT off single vm . 347606|===========================================================================================================================================================================================================================================================================================================================================================

    PostgreSQL pgbench 10.3
    Scaling: Mostly RAM - Test: Single Thread - Mode: Read Only
    TPS > Higher Is Better
    phoronix pgbench 242 HT off single vm . 17920|============================================================================================================================================================================================================================================================================================================================================================

    PostgreSQL pgbench 10.3
    Scaling: Mostly RAM - Test: Heavy Contention - Mode: Read Only
    TPS > Higher Is Better
    phoronix pgbench 242 HT off single vm . 355463|===========================================================================================================================================================================================================================================================================================================================================================
```

- Results Uploaded To: https://openbenchmarking.org/result/1905295-HV-PHORONIXP81

<a id="fourth-test-two-vms-ht-off"></a>
## Fourth Test: Two VMs, HT off

```
phoronix pgbench 242 HT off:
        Processor: 2 x Intel Xeon E5-2690 v4 (32 Cores), Motherboard: Xen HVM domU (4.11.1-7.3.xcpng8.0 BIOS), Chipset: Intel 440FX 82441FX PMC, Memory: 16384 MB + 16376 MB RAM, Disk: 10GB, Graphics: DRM emulated
        OS: CentOS Linux 7, Kernel: 5.1.5-1.el7.elrepo.x86_64 (x86_64), Compiler: GCC 4.8.5 20150623, File-System: ext4, Screen Resolution: 1024x768, System Layer: Xen HVM domU 4.11.1-7.3.xcpng8.0

    PostgreSQL pgbench 10.3
    Scaling: Mostly RAM - Test: Normal Load - Mode: Read Only
    TPS > Higher Is Better
    phoronix pgbench 242 HT off . 199752|=============================================================================================================================================================

    PostgreSQL pgbench 10.3
    Scaling: Mostly RAM - Test: Single Thread - Mode: Read Only
    TPS > Higher Is Better
    phoronix pgbench 242 HT off . 17194|==============================================================================================================================================================

    PostgreSQL pgbench 10.3
    Scaling: Mostly RAM - Test: Heavy Contention - Mode: Read Only
    TPS > Higher Is Better
    phoronix pgbench 242 HT off . 328356|=============================================================================================================================================================
```

- Results Uploaded To: https://openbenchmarking.org/result/1905280-HV-PHORONIXP40

```
phoronix pgbench 242 HT off:
        Processor: 2 x Intel Xeon E5-2690 v4 (32 Cores), Motherboard: Xen HVM domU (4.11.1-7.3.xcpng8.0 BIOS), Chipset: Intel 440FX 82441FX PMC, Memory: 16384 MB + 16376 MB RAM, Disk: 10GB, Graphics: DRM emulated
        OS: CentOS Linux 7, Kernel: 5.1.5-1.el7.elrepo.x86_64 (x86_64), Compiler: GCC 4.8.5 20150623, File-System: ext4, Screen Resolution: 1024x768, System Layer: Xen HVM domU 4.11.1-7.3.xcpng8.0

    PostgreSQL pgbench 10.3
    Scaling: Mostly RAM - Test: Normal Load - Mode: Read Only
    TPS > Higher Is Better
    phoronix pgbench 242 HT off . 207881|=============================================================================================================================================================

    PostgreSQL pgbench 10.3
    Scaling: Mostly RAM - Test: Single Thread - Mode: Read Only
    TPS > Higher Is Better
    phoronix pgbench 242 HT off . 17544|==============================================================================================================================================================

    PostgreSQL pgbench 10.3
    Scaling: Mostly RAM - Test: Heavy Contention - Mode: Read Only
    TPS > Higher Is Better
    phoronix pgbench 242 HT off . 357756|=============================================================================================================================================================
```

- Results Uploaded To: https://openbenchmarking.org/result/1905285-HV-PHORONIXP40


- Total combined TPS - Normal Load - Mode: Read Only: **407,633**
- Total combined TPS - Single Thread - Mode: Read Only: **33,738**
- Total combined TPS - Heavy Contention - Mode: Read Only: **686,112**

---

<a id="performance-impact-of-disabling-hyperthreading"></a>
# Performance Impact of Disabling Hyperthreading

- Total combined TPS - Normal Load - Mode: Read Only - Performance difference with with HT disabled: **16.96% decrease**
- Total combined TPS - Single Thread - Mode: Read Only - Performance difference with HT disabled: **2.8% decrease**
- Total combined TPS - Heavy Contention - Mode: Read Only - DPerformance difference with HT disabled: **3.94 increase**
