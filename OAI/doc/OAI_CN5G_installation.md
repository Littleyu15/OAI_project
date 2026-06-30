# OAI_CN5G_installation
> Refrence :
> [NR_SA_Tutorial_OAI_CN5G](https://gitlab.eurecom.fr/oai/openairinterface5g/-/blob/develop/doc/NR_SA_Tutorial_OAI_CN5G.md#1-scenario)

# Table Of Content
- [Step](#oai-cn5g-pre-requisites)

### OAI CN5G pre requisites 

(Install development、networking tools、Docker Engine、Docker Compose plugin)
> ```
> sudo apt install -y git net-tools putty
> sudo apt update
> 
> sudo apt install -y ca-certificates curl
> sudo install -m 0755 -d /etc/apt/keyrings
> sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
> sudo chmod a+r /etc/apt/keyrings/docker.asc
> echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
> sudo apt update
> sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
> ```
### Add your username to the docker group, otherwise you will have to run in sudo mode.
> ```
> sudo usermod -a -G docker (username)
> reboot
> ```

### Download and copy configuration files

You may encounter a 502 Bad Gateway error; please try again.
> ```
> wget -O ~/oai-cn5g.zip https://gitlab.eurecom.fr/oai/openairinterface5g/-/archive/develop/openairinterface5g-develop.zip?path=doc/tutorial_resources/oai-cn5g
> unzip ~/oai-cn5g.zip
> mv ~/openairinterface5g-develop-doc-tutorial_resources-oai-cn5g/doc/tutorial_resources/oai-cn5g ~/oai-cn5g
> rm -r ~/openairinterface5g-develop-doc-tutorial_resources-oai-cn5g ~/oai-cn5g.zip
> ```
> ### Output
> <img width="989" height="338" alt="image" src="https://github.com/user-attachments/assets/6252616a-0974-43a9-bb46-18d854f2c0f0" />

### Pull OAI CN5G docker images
> ```
> cd ~/oai-cn5g
> docker compose pull
> ```

### Start OAI CN5G
> ```
> cd ~/oai-cn5g
> docker compose up -d
> ```
> ### Output
> <img width="323" height="244" alt="image" src="https://github.com/user-attachments/assets/3ec19d6e-b062-444f-b457-4900373168d2" />

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

### Check whether the containers are healthy
> ```
> watch -n 1 docker compose -f docker-compose.yaml ps -a
> ```
> ### Output
> <img width="1325" height="234" alt="image" src="https://github.com/user-attachments/assets/58cb13b7-7a45-4e72-b969-b4b74e4017aa" />

### Stop OAI CN5G
(Make sure to shut it down when you’re done, otherwise the containers will be left running.)
> ```
> cd ~/oai-cn5g
> docker compose down
> ```
> ### Output
> <img width="332" height="255" alt="image" src="https://github.com/user-attachments/assets/d9a74a67-e950-45e0-893d-abd7e05f6100" />

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
