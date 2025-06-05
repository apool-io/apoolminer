# Apoolminer

```powershell
 $$$$$$\  $$$$$$$\   $$$$$$\   $$$$$$\  $$\       
$$  __$$\ $$  __$$\ $$  __$$\ $$  __$$\ $$ |      
$$ /  $$ |$$ |  $$ |$$ /  $$ |$$ /  $$ |$$ |      
$$$$$$$$ |$$$$$$$  |$$ |  $$ |$$ |  $$ |$$ |      
$$  __$$ |$$  ____/ $$ |  $$ |$$ |  $$ |$$ |      
$$ |  $$ |$$ |      $$ |  $$ |$$ |  $$ |$$ |      
$$ |  $$ |$$ |       $$$$$$  | $$$$$$  |$$$$$$$$\ 
\__|  \__|\__|       \______/  \______/ \________|
```

## Introduction

The best Optimization Miner for Aleo & Qubic.

## Disclaimer

[apool.io](https://www.apool.io/) & [apoolminer_github](https://github.com/apool-io/apoolminer) are the only 2 officially maintained site for publishing information and new releases of apoolminer.

## Install

Always get the lastest version from the [releases](https://github.com/apool-io/apoolminer/releases)

and then extract the file


## Usage

Please refer to the usage help (`./apoolminer --help`):

If you didn't have an apool account, Head over to [Apool Website](https://www.apool.io) to finish email registration, and Copy the sub-account from [myminer page](https://www.apool.io/myMiner).

Then start miner like:

```powershell
./apoolminer --algo qubic --account <your sub-account> --pool <aleo/qubic proxy> [OPTIONS] 
```

```powershell
Options:
      --algo <ALGORITHM>    Specify algorithm, default: qubic
      --account <ACCOUNT>   Specify the sub-account, copy from myminer page
      --worker <WORKER>     Specify the worker name. miner use the machine ip default,
                            Note: The name consists of numbers and letters and cannot exceed 15 characters in length
      --pool <POOL>         Specify the pool proxy for the mining coin, eg. qubic1.hk.apool.io:3334 for qubic
      --cpu-off             Close CPU mining
      --gpu-off             Close GPU mining

  -g, --gpu <GPU>           Specify the index of GPU. Specify multiple times to use multiple GPUs, example: -g 0 -g 1 -g 2. Note: Use all gpus if not specify.
  -t, --thread <T>          Specify the number of CPU thread [default: 0]
  -o, --log <LOG>           Specify the log file

      --mode 0,             default configuration, all data is placed in GPU VRAM, for typical rigs using PCIEx1 channels, please use this mode
      --mode 1,             hybrid mode, part of the data offloaded to the host memory, performance can be increased by about 10%-20%, standard gaming PC or multi-card servers can use this mode,
                            each card needs to consume additional host memory, please make sure that the system has enough memory configuration, you can follow the log to configure.
```

## CPU supports

- Intel/AMD CPUs support AVX2
  
## GPU supports

- NVIDIA Turing GPU (RTX20)
- NVIDIA Ampere GPU (RTX30)
- NVIDIA Ada Lovelace GPU (RTX40)

## API Reference

### miner status 

**Path：** /status

**Method：** GET

**Response:**

```
{
  "code": 200,
  "data": {
    "online": false
  }
}
```

### miner info 

The /gpu API will return all devices, including cpu.

**Path：** /gpu

**Method：** GET

**Response:**  

```
{
"code": 200,
"data": {
    "gpus": [{
        "cclk": 1635, //graphics clock
        "ctmp": 74, // gpu temperature
        "device": "2060SU", //gpu device 
        "fan": 76, //fan
        "gmclk": 6801, //graphics memory clock
        "id": 0,
        "inval": 0, //invalid
        "mtmp": "89", //max temperature
        "power": 169, //power
        "proof": 0.0, //proof rate
        "statle": 0, // statle
        "valid": 0 // valid
    }],
    "uptime": 197 //program up time 
}
```

**Usage:**

```powershell
./apoolminer --algo qubic --account <your sub-account> --rest --port 5001 --pool <coin proxy> [OPTIONS]    
```

## Changelog
### 0.6.0
1. Version for running Aleo testnet3.  
### 1.1.0
1. Version for running Qubic, it is only for CPU now.
### 1.2.1
1. Qubic Epoch 104, support for CPU and NVIDIA GPU.
2. Support Windows10 and Ubuntu18.04-22.04.
### 1.2.3
1. Fix some bug. 
2. Optimal performance.
### 1.2.4
1. Fixed some machine anomalies.
### 1.2.6
1. Fix one bug which may generate invalid share.
2. GPU performance +12% .
### 1.2.7
1. GPU optimal performance, support CPU without avx2.
### 1.2.8
1. CPU and GPU performance optimization.
### 1.2.9
1. Some GPU models performance optimized by 10%-20%.
2. Fix the issue of low computing power of the 4090 GPU cards.
### 1.3.0
1. Qubic epoch 107.
### 1.3.1
1. Fixed some machine anomalies.
### 1.3.2
1. GPU performance improved by 10%.
2. Support automatic upgrade in Linux (Tutorial available on the official website).
3. Some bugs have been fixed.
### 1.4.0
1. Qubic epoch 109.
2. HiveOS has been upgraded to an automatically updated version.
3. Windows has been upgraded to an automatically updated version.
### 1.4.1
1. CPU and GPU performance optimization.
### 1.4.2
1. GPU performance optimization.
### 1.4.3
1. GPU performance optimization.
### 1.5.0
1. Qubic epoch 112.
### 1.5.1
1. Performance / efficiency improvements (Both CPU and GPU, 5%-15%).
### 1.5.2
1. Performance / efficiency improvements (Both CPU and GPU, 5%-15%).
### 1.6.0
1. Qubic epoch 114.
### 1.6.1
1. Fixed some bug.
### 1.6.2
1. Performance improvement in linux environment.
2. Performance improvement for NVIDIA RTX20 Cards, about 5%.
### 1.6.3
1. CPU mining with Aleo support.
### 1.6.4
1. CPU performance optimization for Aleo.
### 1.6.5
1. Aleo support GPU mining.
### 1.6.6
1. Performance optimization for Aleo.
### 1.6.7
1. CPU performance improved by 10% for Aleo.
### 1.6.8
1. CPU performance improved by 30% for Aleo.
### 1.6.9
1. CPU and GPU performance improved by 10%-15% for Aleo.
### 1.6.10
1. CPU performance improved by 30% for Aleo.
### 1.6.11
1. GPU performance improved by 20% for Qubic.
### 1.6.12
1. Fixed an automatic update issue for Qubic in HiveOS(This version only support Qubic).
### 1.6.13
1. GPU performance improved by 30% for Qubic.
### 1.6.14
1. GPU performance improved by 110% for Qubic.
### 1.6.15
1. The GPU support hybrid mode (--mode 1) to mine Qubic.
2. Performance increased by about 10%-20% in mode 1, increased by about 5% in mode 0.
### 1.7.0
1. Qubic epoch 121.
### 1.7.1
1. GPU performance improved by 10% for Qubic.
### 1.7.2
1. CPU performance improved by 50% for Qubic.
### 1.8.0
1. Qubic epoch 122.
### 1.8.1
1. Support ore solo cpu mining.
### 1.9.0
1. Qubic epoch 123.
### 1.9.1
1. CPU performance improved by 100% for Ore.
2. GPU and CPU performance improved by 10% for Qubic.
### 1.9.2
1. CPU performance improved by 20% for Qubic.
2. Bug fix for Ore.
### 1.9.3
1. GPU performance improved by 20% for Qubic.
### 1.9.4
1. CPU performance improved by 20% for Qubic.
### 1.9.5
1. GPU performance improved by 20% for Qubic.
### 2.0.0
1. Qubic epoch 125.
### 2.1.0
1. Qubic epoch 126.
### 2.1.1
1. GPU and CPU performance optimization for Qubic.
### 2.1.2
1. GPU and CPU performance improved by 15% for Qubic.
### 2.2.0
1. Qubic epoch 128.
2. Support ore pool and gpu mining.
### 2.2.1
1. GPU performance improved by 25% for Qubic.
### 2.2.2
1. GPU performance improved by 15%-20% for Qubic.
### 2.3.0
1. Qubic epoch 129.
2. Support ore and qubic dual mining.
### 2.3.1
1. GPU performance improved by 50% for ORE.
2. Fix bug.
### 2.4.0
1. Qubic epoch 130.
2. GPU performance improved by 20% for ORE.
3. Fix bug about dual mining.
### 2.4.1
1. Fix bug.
### 2.4.2
1. GPU performance improved by 15%-20% for Qubic.
### 2.4.3
1. CPU performance improved by 50% for Qubic.
### 2.5.0
1. Qubic epoch 131.
### 2.5.1
1. Fixed some gpu failure issues.
### 2.6.0
1. Qubic epoch 132.
### 2.6.1
1. 15% performance increase for RTX30s and RTX40s, 10% performance increase for RTX20s
2. Reduced GPU resource usage, can support true Dual mining with zkminer without affecting Qubic performance, unlike Idle mining, you can get 60% extra Aleo rewards in Qubic cycle.
### 2.6.2
1. GPU performance improved by 20%-30% for Qubic.
2. CPU performance improved by 100%-150% for Qubic.
### 2.6.3
1. GPU performance improved by 30% for Qubic.
2. CPU performance improved by 35% for Qubic.
### 2.6.4
1. GPU performance improved by 35% for Qubic.
2. CPU performance improved by 20% for Qubic.
### 2.6.5
1. CPU and GPU performance optimization for Qubic.
### 2.6.6
1. GPU performance improved by 20% for Qubic.
2. CPU performance improved by 20%-30% for Qubic.
### 2.6.7
1. Fix the Qubic CPU core count bug in Windows environment.
2. Qubic RTX30s GPU performance increased by about 8%, others increased by about 5%.
3. ORE mining switched to the latest Boost protocol, the revenue increased by more than 100% (after upgrading the version, the mining revenue will appear under the new ore-boost account, the old ore account balance will not be automatically merged, please withdraw the money manually).
### 2.7.0
1. Qubic epoch 138.
### 2.7.1
1. Emergency bug fixed.
### 2.7.2
1. Fixed the bug in the Windows version that caused low hashrate on 4090 GPUs.
### 2.7.3
1. CPU and GPU performance optimization for Qubic.
### 2.7.4
1. GPU performance optimization for Qubic.
### 2.7.5
1. GPU performance improved by 100%.
### 2.7.6
1. ORE fixes bugs, GPU performance increased by 20%, ORE users please replace the new version as soon as possible, the old version will stop support on December 25th!
### 2.7.6
1. Fixed the rejection rate issue in the ORE Windows version.
2. GPU performance improved by 10%-20%.
### 2.7.9
1. GPU and CPU performance improved by 600%-800% for Qubic.
### 2.7.10
1. GPU performance improved by 10% for Qubic.
### 2.8.0
1. Qubic epoch 143.
### 2.8.1
1. Qubic GPU performance improved by 40%.
2. Qubic CPU performance improved by 50%.
### 2.8.2
1. GPU and CPU performance improved by 30%-50% for Qubic.
### 2.8.4
1. Fix some bugs in the Windows version.
2. Optimized the logic for currency switching during idle time.
### 2.8.6
1. Qubic supports the NVIDIA 50 series GPUs.
2. Qubic GPU performance improved by 8%.
### 2.9.0
1. Epoch 161.
2. Miner adds support for QXMR.
### 2.9.1
1. Fixed an issue where some CPUs experienced hashrate drops.
2. Added option to set the number of threads for XMR mining.
3. Added a toggle to enable or disable CPU mining for XMR.
### 2.9.2
1. Added TLS/SSL encrypted connection support (Qubic, XMR)
（qubic：qubic1.hk.apool.io:2334、qubic2.hk.apool.io:2334）（xmr：xmr.hk.apool.io:2334）
2. Fixed MSR-related issues on Windows
3. Resolved GPU mining issues on XMR for machines with 4GB RAM
