<img width="294" height="109" alt="image" src="https://github.com/user-attachments/assets/7f267db2-06cc-44b9-a469-c6b5e4c93026" /># OAI_5G_NR_SA_tutorial_with_OAI_nrUE
> Refrence : [OAI 5G NR SA tutorial with OAI nrUE](https://gitlab.eurecom.fr/oai/openairinterface5g/-/blob/develop/doc/NR_SA_Tutorial_OAI_nrUE.md?ref_type=heads#oai-5g-nr-sa-tutorial-with-oai-nrue)

# Table Of Content 
- [Scenario](#scenario)
- [Step](#oai-cn5g-setup)

  
### Scenario
Minimum hardware requirements :
- Laptop/Desktop/Server for **OAI CN5G** and **OAI gNB**
  - Operating System: [Ubuntu 24.04 LTS](https://releases.ubuntu.com/noble/)
  - CPU: 8 cores x86_64 @ 3.5 GHz
  - RAM: 32 GB
- Laptop for **UE**:
  - Operating System: [Ubuntu 24.04 LTS](https://releases.ubuntu.com/noble/)
  - CPU: 8 cores x86_64 @ 3.5 GHz
  - RAM: 8 GB
 
  
### [OAI CN5G Setup](https://github.com/Littleyu15/OAI_project/blob/main/OAI/OAI_CN5G_installation.md#oai_cn5g_installation)

### OAI gNB and OAI nrUE pre-requisites
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

### Build OAI gNB and OAI nrUE
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

### Run OAI CN5G and OAI gNB
