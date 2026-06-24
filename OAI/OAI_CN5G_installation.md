# OAI_CN5G_installation.
> Refrence :
> [NR_SA_Tutorial_OAI_CN5G](https://gitlab.eurecom.fr/oai/openairinterface5g/-/blob/develop/doc/NR_SA_Tutorial_OAI_CN5G.md#2-oai-cn5g)

# Table Of Content
- [Scenario](#scenario)
- [Step](#oai-cn5g-pre-requisites)


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
