## Setting up Kali Linux and More
- in this course we will be using Kali Linux and some of its built in tools like Postman, Burpsuite, wfuzz or Kiterunner
- Burpsuite
	- The tool for monitoring web traffic and manipulating it
	- you have to download the CA certificate by navigating to http://burpsuite, clicking the CA certificate button up right and importing it into your web-browsers trusted CA certificates list - you have to have your Foxy-Proxy and Burpsuite turned on for this to work
	- you should also install the Autorize extension for Burpsuite
 Foxy-Proxy
	- web-browser extension that allows you to redirect your browser traffic through a proxy server (we will configure it to pass the traffic through us (127.0.0.1)) - on a specific port, with a specific proxy type (HTTP/SOCKS)
	- this tool will be used along with Burpsuite and Postman
- Postman
	- some kind of tool we will use, created a workspace name ACE
- python tool: mitmproxy2swagger
	- installed to /opt with *sudo pip3 install mitmproxy2swagger*
- jwt_tool
	- cloned from this repository: https://github.com/ticarpi/jwt_tool
	- jwt stands for JSON Web Token
	- created a shortcut: ln -s /opt/jwt_tool/jwt_tool.py /usr/bin/jwt_tool
- Kiterunner
	- cloned from this repository: https://github.com/assetnote/kiterunner.git
	- created a shortcut: ln -s /opt/kiterunner/dist/kr /usr/bin/kr
- zap
	- some kind of vulnerability scanner
	- already installed on my machine
- other explicitly installed tools (with apt):
	- git, docker.io, docker-compose, golang-go
## Your API Hacking Lab
- we will be using two vulnerable web-services throughout this course (crAPI and vAPI)
- crAPI
	- short for The Completely Ridiculous API
	- installed from this link: https://raw.githubusercontent.com/OWASP/crAPI/main/deploy/docker/docker-compose.yml
	- ran: sudo docker-compose pull
	- ran: sudo docker-compose -f docker-compose.yml (downloaded file) --compatibility up -d
	- localhost:8888 = main crAPI page
	- localhost:8025 = mailhog (mail server)
	- containers under this compose:
		- crapi-web
		- crapi-community
		- crapi-workshop
		- crapi-identify
		- mailhog
		- mongodb
		- posgresdb
	- to list the running containers, use: sudo docker-compose ls
	- to stop the running containers, use: sudo docker-compose stop
	- to start the running containers, cd to the path where you have the docker-compose.yaml file and use: sudo docker-compose start
- vAPI
	- cloned a repository: git clone https://github.com/roottusk/vapi.git
	- composed: sudo docker-compose up -d
	- localhost:80 - main page (try /vapi)
	- containers under this compose:
		- vapi_db_1
		- vapi_www_1
		- vapi_phpmyadmin_1
	- to list the running containers, use: sudo docker-compose ls
	- to stop the running containers, use: sudo docker-compose stop
## Lab Setup Quiz
### The test
1. What is the primary operating system that will be used throughout the API Penetration Testing course? (one)
	1. ParrotOS
	2. Kali Linux
	3. Windows 10
	4. MacOS Sierra
2. What are the primary tools used for the API Penetration Testing course? (one)
	1. MassScan, NetCat, SMBClient, Postman and RPCclient
	2. Kiterunner, Git, Maltego, Nikto, Dirbuster and BurpSuite
	3. Amass, Legion, Sublist3r, Metasploit and Swagger
	4. Postman, Amass, BurpSuite, WFuzz, Kiterunner and JWT_Tool
3. Which two deliberately vulnerable applications are used throughout the API Penetration Testing course? (one)
	1. crAPI + vAPI
	2. DVGA + DVGQL
	3. vAmPI + crAPI
	4. crAPI + Pixi
4. What three educational platforms can be used to find other API hacking labs? (more)
	1. TryHackMe
	2. GitHub
	3. HackTheBox
	4. The Wayback Machine
5. When starting a new operating system it is always a good idea to: (one)
	1. Create a hapihacker user account
	2. Update the system
	3. Change the default credentials
	4. B & C
6. When using a command line tool like JWT_tool what commands/options can be used to learn how to use it? (more)
	1. $jwt_tool -a
	2. $jwt_tool -h
	3. $jwt_tool --help
	4. $jwt_tool
	5. $man jwt_tool

### The solution
1. What is the primary operating system that will be used throughout the API Penetration Testing course? (one)
	1. ParrotOS
	2. **Kali Linux**
	3. Windows 10
	4. MacOS Sierra
2. What are the primary tools used for the API Penetration Testing course? (one)
	1. MassScan, NetCat, SMBClient, Postman and RPCclient
	2. Kiterunner, Git, Maltego, Nikto, Dirbuster and BurpSuite
	3. Amass, Legion, Sublist3r, Metasploit and Swagger
	4. **Postman, Amass, BurpSuite, WFuzz, Kiterunner and JWT_Tool**
3. Which two deliberately vulnerable applications are used throughout the API Penetration Testing course? (one)
	1. **crAPI + vAPI**
	2. DVGA + DVGQL
	3. vAmPI + crAPI
	4. crAPI + Pixi
4. What three educational platforms can be used to find other API hacking labs? (more)
	1. **TryHackMe**
	2. **GitHub**
	3. **HackTheBox**
	4. The Wayback Machine
5. When starting a new operating system it is always a good idea to (one):
	1. Create a hapihacker user account
	2. Update the system
	3. Change the default credentials
	4. **B & C**
6. When using a command line tool like JWT_tool what commands/options can be used to learn how to use it? (more)
	1. $jwt_tool -a
	2. **$jwt_tool -h**
	3. **$jwt_tool --help**
	4. **$jwt_tool**
	5. **$man jwt_tool**