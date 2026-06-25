# OAI_5G_NR_SA_tutorial_with_OAI_nrUE
> Refrence : [OAI 5G NR SA tutorial with OAI nrUE](https://gitlab.eurecom.fr/oai/openairinterface5g/-/blob/develop/doc/NR_SA_Tutorial_OAI_nrUE.md?ref_type=heads#oai-5g-nr-sa-tutorial-with-oai-nrue)

# Table Of Content 
- [Scenario](#scenario)
- [Step](#oai-cn5g-setup)

  
### 💻Scenario
Minimum hardware requirements :
- Laptop/Desktop/Server for **OAI CN5G** and **OAI gNB**
  - Operating System: [Ubuntu 24.04 LTS](https://releases.ubuntu.com/noble/)
  - CPU: 8 cores x86_64 @ 3.5 GHz
  - RAM: 32 GB
- Laptop for **UE**:
  - Operating System: [Ubuntu 24.04 LTS](https://releases.ubuntu.com/noble/)
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

## 4️⃣Run OAI CN5G and OAI gNB
we need three terminal to run E2E

### 4️-1️ Run OAI CN5G
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


### 4️-2️ Run OAI gNB
> Refrence : https://gitlab.eurecom.fr/oai/openairinterface5g/-/blob/develop/doc/NR_SA_Tutorial_OAI_nrUE.md?ref_type=heads#42-run-oai-gnb
> ```
> # second terminal
> # RFsim mode (radio function simulator)
> cd ~/openairinterface5g/cmake_targets/ran_build/build
> sudo ./nr-softmodem -O ../../../targets/PROJECTS/GENERIC-NR-5GC/CONF/gnb.sa.band78.fr1.106PRB.usrpb210.conf --gNBs.[0].min_rxtxtime 6 --rfsim
> ```
> ### Output
> <img width="658" height="488" alt="image" src="https://github.com/user-attachments/assets/63886583-b26d-4cf4-871e-fcbfa76e3cfd" />


### 4️-3️ Run OAI nrUE
> Refrence : https://gitlab.eurecom.fr/oai/openairinterface5g/-/blob/develop/doc/NR_SA_Tutorial_OAI_nrUE.md?ref_type=heads#51-run-oai-nrue
> ```
> # third terminal
> # RFsim mode (radio function simulator)
> # The UE configuration must match the one of the network's AMF, so one can specify the nrUE configuration file adding address 127.0.0.1 behind --rfsim
> 
> cd ~/openairinterface5g/cmake_targets/ran_build/build
> sudo ./nr-uesoftmodem -r 106 --numerology 1 --band 78 -C 3619200000 --uicc0.imsi 001010000000001 --rfsim --rfsimulator.serveraddr 127.0.0.1
> ```
> ### Output
> <img width="702" height="521" alt="image" src="https://github.com/user-attachments/assets/64aa0423-fd71-4acb-bc64-172a39cc1a2d" />

### 5️⃣Check nrUE amf log 

log

> ```
> docker logs oai-amf --tail 50
> ```
> ### Output
> <img width="1284" height="887" alt="image" src="https://github.com/user-attachments/assets/923cea64-3429-4f58-b752-c22d40ec1f06" />


