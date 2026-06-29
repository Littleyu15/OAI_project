# OAI O1 Adapter Manual

## Table Of Content
- [Introduction](#introduction)
- [Scenario](#system-integration-diagram)
- [Step](#run-o1-adapter)


## Introduction
This guide covers building, configuring, and running the OAI O1 Adapter. The O1 Adapter acts as a mediator bridging the OAI gNB (using Telnet commands) with the SMO layer (via O1 interfaces such as VES Collector and NETCONF).


## System Integration Diagram

```mermaid
graph TD
    %% Define Styles
    classDef host fill:#2ca02c,stroke:#1b5e20,stroke-width:2px,color:#fff;
    classDef docker fill:#1f77b4,stroke:#0d47a1,stroke-width:2px,color:#fff;
    classDef smo fill:#9467bd,stroke:#4a148c,stroke-width:2px,color:#fff;

    subgraph gNB_Host ["gNB Host (Ubuntu)"]
        subgraph Docker_Container ["Docker Container (adapter-gnb)"]
            O1_Adpt["OAI O1 Adapter"]:::docker
            Conf["config.json"]:::docker
            O1_Adpt --- Conf
        end
        
        gNB_Modem["OAI gNB Modem<br/>(nr-softmodem with telnetsrv)"]:::host
    end

    subgraph SMO_Management ["SMO Layer"]
        VES["VES Collector<br/>(Port 30417)"]:::smo
        NETCONF["NETCONF Client (SMO)"]:::smo
    end

    %% Communications
    O1_Adpt --- |"Local Telnet (Port 9090)<br/>Query & Event Monitoring"| gNB_Modem
    O1_Adpt -->|"HTTP Post (O1 VES)<br/>prachAttackDetected Alarms"| VES
    NETCONF <-->|"NETCONF SSH (Port 1830)"| O1_Adpt
```


### Run O1 Adapter

```
cd o1-adapter
sudo ./start-adapter.sh --adapter
```


### Stop and Remove O1 Adapter

```
sudo docker stop adapter-gnb
sudo docker rm adapter-gnb
```
