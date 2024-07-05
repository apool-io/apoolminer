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

Alawys get the lastest version from the [releases](https://github.com/apool-io/apoolminer/releases)

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
      --algo <ALGORITHM>     Specify algorithm, default: qubic
      --account <ACCOUNT>    Specify the sub-account, copy from myminer page
      --worker <WORKER>     Specify the worker name. miner use the machine ip default,
                            Note: The name consists of numbers and letters and cannot exceed 15 characters in length
      --pool <POOL>         Specify the pool proxy for the mining coin, eg. qubic1.hk.apool.io:3334 for qubic
      --cpu-off             Close CPU mining
      --gpu-off             Close GPU mining

  -g, --gpu <GPU>           Specify the index of GPU. Specify multiple times to use multiple GPUs, example: -g 0 -g 1 -g 2. Note: Use all gpus if not specify.
  -t, --thread <T>          Specify the number of CPU thread [default: 0]
  -o, --log <LOG>          Specify the log file
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
1. CPU performance optimization for Aleo.
