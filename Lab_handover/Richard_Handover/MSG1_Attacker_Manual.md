# MSG1 Jamming Attacker Manual

# Table Of Content
- [Introduction](#introduction)
- [Scenario](#scenario)
  - [Minimum hardware requirements](#minimum-hardware-requirements)
- [Step](#quick-re-buildafter-edit)
## Introduction
This document explains how to configure, build, and run the MSG1 Jamming Attacker based on OAI (OpenAirInterface).

## Scenario

### Attacker Setup Diagram

```mermaid
graph TD
    %% Define Styles
    classDef host fill:#2ca02c,stroke:#1b5e20,stroke-width:2px,color:#fff;
    classDef proc fill:#1f77b4,stroke:#0d47a1,stroke-width:2px,color:#fff;
    classDef sdr fill:#ff7f0e,stroke:#e65100,stroke-width:2px,color:#fff;
    classDef target fill:#d50000,stroke:#b71c1c,stroke-width:2px,color:#fff;

    subgraph Attacker_Node ["Attacker Node (Ubuntu Host)"]
        Host["Ubuntu 24.04 LTS Host"]:::host
        Process["OAI UE Attacker Process<br/>(nr-uesoftmodem)"]:::proc
        UHD["UHD Driver (SDR Interface)"]:::proc
        
        Host --- Process
        Process --- UHD
    end

    USRP["USRP SDR Device<br/>(B210 / N300 / X300)"]:::sdr
    gNB["OAI gNB<br/>(Target Base Station)"]:::target

    UHD --- |"USB / PCIe / Ethernet"| USRP
    USRP --- |"RF Jamming (Uu Interface)"| gNB
```

### Minimum hardware requirements 

- **Laptop for the MSG1 attacker**
    - Operating System: Ubuntu 24.04 LTS (https://releases.ubuntu.com/24.04/ubuntu-24.04.2-desktop-amd64.iso)
    - CPU: 8 cores x86_64 @ 3.5 GHz
    - RAM: 8 GB
- **Supported USRPs:** USRP B210, USRP N300, or USRP X300
    - Identify the network interface(s) where the USRP is connected and update the gNB configuration accordingly.
 

### Quick Re-build(after edit)
```
cd ~/OAI-UE-MSG1-attacker/cmake_targets/ran_build/build
sudo ninja nr-softmodem nr-uesoftmodem dfts ldpc params_libconfig
```

### Execute Attacker (USRP B210)

> [!IMPORTANT]
> Run the attacker on a separate host from the gNB (for example, a second Ubuntu 22.04 machine).


After building and entering the build folder, start the UE softmodem with:

```
cd OAI-UE-MSG1-attacker/cmake_targets/ran_build/build
sudo ./nr-uesoftmodem -r 106 --numerology 1 --band 78 -C 3619200000 --ssb 516 -E --ue-fo-compensation
```

### Notes on parameters

- `C <frequency>`: The value passed to `C` is the center frequency in Hz, computed from the SSB ARFCN. Convert the SSB ARFCN to the corresponding frequency (Hz) and provide that value to `C`.
- `-ssb <offset>`: The value passed to `-ssb` is the SSB index/offset used to select the specific SSB within the carrier.

### Available options

- `-ue-txgain <value>`: Adjust UE transmit power (tx gain). Example: `-ue-txgain 120`.
- `-ue-rxgain <value>`: Adjust UE receive gain (rx gain). Example: `-ue-rxgain 120`.
- `att_tx <value>`: Adjust gNB transmit power (if supported by the attacker tool).
- `att_rx <value>`: Adjust gNB receive gain (if supported by the attacker tool).
