# OAI_CN5G_installation
> Refrence :
> [NR_SA_Tutorial_OAI_CN5G](https://gitlab.eurecom.fr/oai/openairinterface5g/-/blob/develop/doc/NR_SA_Tutorial_OAI_nrUE.md?ref_type=heads#oai-5g-nr-sa-tutorial-with-oai-nrue)

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

