# OAI_5G_NR_SA_tutorial_with_OAI_nrUE
> Refrence : [OAI 5G NR SA tutorial with OAI nrUE](https://gitlab.eurecom.fr/oai/openairinterface5g/-/blob/develop/doc/NR_SA_Tutorial_OAI_nrUE.md?ref_type=heads#oai-5g-nr-sa-tutorial-with-oai-nrue)

# Table Of Content 
- [Scenario](#scenario)
- [Step](#oai-gnb-and-oai-nrue-pre-requisites)

  
### 💻Scenario
Minimum hardware requirements :
- Laptop/Desktop/Server for **OAI CN5G** and **OAI gNB**
  - Operating System: Ubuntu 24.04 LTS[(Download)](https://releases.ubuntu.com/noble/)
  - CPU: 8 cores x86_64 @ 3.5 GHz
  - RAM: 32 GB
- Laptop for **UE**:
  - Operating System: Ubuntu 24.04 LTS[(Download)](https://releases.ubuntu.com/noble/)
  - CPU: 8 cores x86_64 @ 3.5 GHz
  - RAM: 8 GB
 
  
### 1️⃣[OAI CN5G Setup](https://github.com/Littleyu15/OAI_project/blob/main/OAI/OAI_CN5G_installation.md#oai_cn5g_installation)

### 2️⃣OAI gNB and OAI nrUE pre-requisites
(Build UHD from source)
> ```
> # https://files.ettus.com/manual/page_build_guide.html
> sudo apt install -y autoconf automake build-essential ccache cmake cpufrequtils doxygen ethtool g++ git inetutils-tools libboost-all-dev libncurses-dev libusb-1.0-0 libusb-1.0-0-dev libusb-dev python3-dev python3-mako python3-numpy python3-requests python3-scipy python3-setuptools python3-ruamel.yaml
> 
> git clone https://github.com/EttusResearch/uhd.git ~/uhd
> cd ~/uhd
> git checkout v4.8.0.0
> cd host
> mkdir build
> cd build
> cmake ../
> make -j $(nproc)
> make test # This step is optional
> sudo make install
> sudo ldconfig
> sudo uhd_images_downloader
> ```

### 3️⃣Build OAI gNB and OAI nrUE
> ```
> # Get openairinterface5g source code
> git clone https://github.com/duranta-project/openairinterface5g.git ~/openairinterface5g
> cd ~/openairinterface5g
> git checkout develop
> 
> # Install OAI dependencies
> cd ~/openairinterface5g/cmake_targets
> ./build_oai -I
> 
> # nrscope dependencies
> sudo apt install -y libforms-dev libforms-bin
> 
> # Build OAI gNB
> cd ~/openairinterface5g/cmake_targets
> ./build_oai -w USRP --ninja --nrUE --gNB --build-lib "nrscope" -C
> ```

### 4️⃣Installation of dependencies and compilation(安裝相依套件與編譯)
> ```
> cd openairinterface5g
> git checkout 2025.w46                        # tested tag
> cd cmake_targets
> ./build_oai --ninja -I                       # install dependencies
> 
> ./build_oai --ninja --gNB --nrUE -w SIMU -c  # compile gNB and nrUE 
> ```

## 5️⃣Run OAI CN5G and OAI gNB
we need three terminal to run E2E

### 5️-1️ Run OAI CN5G
> ```
> # first terminal
> # remember to shut it down when you're done
> 
> cd ~/oai-cn5g
> docker compose up -d
> 
> # Check whether the containers are healthy
> watch -n 1 docker compose -f docker-compose.yaml ps -a
> ```
> ### Output
location: `/oai-cn5g/docker-compose.yaml`
> ```
> Container oai-ext-dn  1.6s  # External Data Network(外部數據網路): Simulates external internet and routes traffic.
> Container oai-nrf     1.5s  # Network Repository Function(網路儲存庫功能): Service registration and discovery center.
> Container mysql       1.6s  # MySQL Database(MySQL 資料庫): Stores subscriber data and network configurations.
> Container ims         1.3s  # IP Multimedia Subsystem(IP 多媒體子系統): Handles SIP-based services (VoLTE/VoNR).
> Container oai-udr     0.6s  # Unified Data Repository(統一資料庫): Backend data access layer for UDM.
> Container oai-udm     0.7s  # Unified Data Management(統一資料管理): Manages user identities and authentication keys.
> Container oai-ausf    0.7s  # Authentication Server Function(認證伺服器功能): Handles security and UE authentication.
> Container oai-amf     0.8s  # Access and Mobility Management Function(存取與移動性管理功能): Handles UE signaling and mobility.
> Container oai-smf     0.6s  # Session Management Function(會話管理功能): Manages data sessions and IP allocation.
> Container oai-upf     0.8s  # User Plane Function(使用者平面功能): Routes and forwards user data packets.
> ```

當一個 5G 設備要求上網時，`AMF` 處理連線，`AUSF`/`UDM`/`UDR`/`MySQL` 確認身分，`SMF` 建立上網通道並發配 IP，最後由 `UPF` 負責將設備的資料轉到 `Ext-DN` 完成上網。

[中文版](#5gc-中文)

### 5️-2️ Run OAI gNB
> Refrence : https://gitlab.eurecom.fr/oai/openairinterface5g/-/blob/develop/doc/NR_SA_Tutorial_OAI_nrUE.md?ref_type=heads#42-run-oai-gnb
> ```
> # second terminal
> # RFsim mode (radio function simulator)
> cd ~/openairinterface5g/cmake_targets/ran_build/build
> sudo ./nr-softmodem -O ../../../targets/PROJECTS/GENERIC-NR-5GC/CONF/gnb.sa.band78.fr1.106PRB.usrpb210.conf --gNBs.[0].min_rxtxtime 6 --rfsim
> ```
> ### Output
> <img width="658" height="488" alt="image" src="https://github.com/user-attachments/assets/63886583-b26d-4cf4-871e-fcbfa76e3cfd" />

#### Parameter Description

- `./nr-softmodem`: Execute the OAI gNB software modem program *(執行 OAI 的 gNB 軟體 modem 程式)*
- `-O ../../../targets/PROJECTS/GENERIC-NR-5GC/CONF/gnb.sa.band78.fr1.106PRB.usrpb210.conf`: go to file destination and choose config.
- `--gNBs.[0].min_rxtxtime 6`: The first gNB node minimum RX-to-TX time, means 6 slots.
- `--rfsim`: RF simulator, dont need hardware



### 5️-3️ Run OAI nrUE
> Refrence : https://gitlab.eurecom.fr/oai/openairinterface5g/-/blob/develop/doc/NR_SA_Tutorial_OAI_nrUE.md?ref_type=heads#51-run-oai-nrue
> ```
> # third terminal
> # RFsim mode (radio function simulator)
> # The UE configuration must match the one of the network's AMF, so one can specify the nrUE configuration file adding address 127.0.0.1 behind --rfsim
> 
> cd ~/openairinterface5g/cmake_targets/ran_build/build
> sudo ./nr-uesoftmodem -r 106 --numerology 1 --band 78 -C 3619200000 --uicc0.imsi 001010000000001 --rfsim --rfsimulator.serveraddr 127.0.0.1
> ```
> 
> ### Output
> <img width="702" height="521" alt="image" src="https://github.com/user-attachments/assets/64aa0423-fd71-4acb-bc64-172a39cc1a2d" />

#### Parameter Description
- `./nr-uesoftmodem`: Execute the OAI UE software modem program.
- `-r <value>`:Number of Resource Block
- `--numerology <value>`: Subcarrier Spacing（SCS）。 A value of 1 indicates 30 kHz (2^1 × 15 kHz). *(子載波的間距)*
- `--band 78`: Use the **n78 (3.3-3.8 GHz)frequency band**.
- `C <frequency>`: The value passed to `C` is the center frequency in Hz, computed from the SSB ARFCN. Convert the SSB ARFCN to the corresponding frequency (Hz) and provide that value to `C`.
- `--uicc0.imsi 001010000000001`: USIM Card IMSI (Simulated SIM Card)
- `--rfsim`: RF simulator, dont need hardware
- `--rfsimulator.serveraddr 127.0.0.1`: Connect to the local RF simulator server



- 
### 5️⃣Check nrUE amf log 

[Log Description](https://github.com/Littleyu15/OAI_project/blob/main/OAI/Background%20knowledge/Log_description.md#table-of-content)

> ```
> docker logs oai-amf --tail 50
> ```
> ### Output
> <img width="1284" height="887" alt="image" src="https://github.com/user-attachments/assets/923cea64-3429-4f58-b752-c22d40ec1f06" />



---

### 5GC 中文

以下是 Docker Compose 成功啟動的容器清單，以及各個容器對應的 5G 網路功能說明：

| 容器名稱 (Container) | 全名 (Full Name) | 核心功能與說明 |
| :--- | :--- | :--- |
| **`oai-ext-dn`** | External Data Network | **外部數據網路**：模擬網際網路節點，內含路由與 `iperf3` 測速工具，用於測試設備上網與流量傳輸。 |
| **`oai-nrf`** | Network Repository Function | **網路儲存庫功能**：服務註冊中心。所有節點啟動時向其註冊，用於微服務間互相尋找 IP 與服務。 |
| **`mysql`** | MySQL Database | **基礎資料庫**：儲存 5G 核心網持久化資料（包含用戶訂閱資訊、SIM 卡認證金鑰與網路配置）。 |
| **`ims`** | IP Multimedia Subsystem | **IP 多媒體子系統**：提供 SIP 服務（基於 Asterisk），處理語音與多媒體通訊，用於 VoLTE/VoNR 測試。 |
| **`oai-udr`** | Unified Data Repository | **統一資料庫**：作為資料存取層，負責將 UDM 所需的策略與用戶資料從 MySQL 中讀取出來。 |
| **`oai-udm`** | Unified Data Management | **統一資料管理**：管理用戶身分識別、權限與服務配置，並負責生成認證金鑰交給 AUSF。 |
| **`oai-ausf`** | Authentication Server Function | **認證伺服器功能**：處理設備接入時的安全性與身分驗證，確保連線的 SIM 卡為合法授權用戶。 |
| **`oai-amf`** | Access & Mobility Mgt. Function| **存取與移動性管理**：處理終端設備的控制信號，管理設備註冊、連線建立與基地台切換 (Handover)。 |
| **`oai-smf`** | Session Management Function | **會話管理功能**：負責管理用戶資料連線，分配 IP 並下達指令控制 UPF 該如何轉發封包。 |
| **`oai-upf`** | User Plane Function | **使用者平面功能**：資料轉發路由器。負責解開基地台送來的 GTP 隧道封包，並轉發至外部網路。 |

 **💡 啟動架構備註：**
 從啟動順序可以看出，系統優先啟動基礎設施（`mysql`, `oai-ext-dn`）與核心註冊中心（`oai-nrf`），接著載入資料庫介接與認證模組（`udr`, `udm`, `ausf`），最後才啟動處理控制信號與網路傳輸的核心管理節點（`amf`, `smf`, `upf`）。
