# OAI gNB Manual 

## Table Of Content
- [Introduction](#introduction)
- [Scenario](#system-integration-diagram)
- [Step](#run-modem)

## Introduction
This guide covers building and running the OAI gNB with telnetsrv enabled, which is required for the O1 Adapter to function.


## System Integration Diagram
```mermaid
graph TD
    %% Define Styles
    classDef host fill:#2ca02c,stroke:#1b5e20,stroke-width:2px,color:#fff;
    classDef proc fill:#1f77b4,stroke:#0d47a1,stroke-width:2px,color:#fff;
    classDef sdr fill:#ff7f0e,stroke:#e65100,stroke-width:2px,color:#fff;
    classDef smo fill:#9467bd,stroke:#4a148c,stroke-width:2px,color:#fff;

    subgraph gNB_Host ["gNB Host (Ubuntu)"]
        gNB_Process["OAI gNB Process<br/>(nr-softmodem)"]:::proc
        TelnetSrv["telnetsrv Shared Lib<br/>(Port 9090)"]:::proc
        O1_Adpt["OAI O1 Adapter"]:::proc
        gNB_Process --- TelnetSrv
    end

    subgraph SMO_Layer ["SMO Management Layer"]
        VES["VES Collector"]:::smo
        NETCONF["NETCONF Server"]:::smo
    end

    RU["Radio Unit"]:::sdr

    %% Connections
    gNB_Process --- |"(Fronthaul)"| RU
    O1_Adpt --- |"Telnet Commands (Port 9090)"| TelnetSrv
    O1_Adpt -->|"VES Events (O1)"| VES
    O1_Adpt <-->|"NETCONF (O1)"| NETCONF
```

### Run Modem 
```
cd openairinterface5g/cmake_targets/ran_build/build

# O1 telnet enable
sudo ./nr-softmodem -O ../../../targets/PROJECTS/GENERIC-NR-5GC/CONF/gnb.sa.band78.fr1.106PRB.usrpb210.conf --gNBs.[0].min_rxtxtime 6 -E --continuous-tx --log_config.PRACH_debug --telnetsrv --telnetsrv.shrmod o1
```
