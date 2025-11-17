# BLU-OEN.github.io
Blog Post




Creating an OpenVAS Server for vulnerability scans on other devices.


For this OpenVAS/Greenbone server I am going to be using Ubtuntu 24.04.3 LTS and Docker.

__Docker__
Using this command we download the docker installtion script
    (''curl -fsSL https://get.docker.com -o get-docker.sh'')

We are going to be using docker to "Dock" the OpenVAS/Greenbone server.

Now we need to make the script we've downloaded executable;

(''chmod +x get-docker.sh'')

then execute the script

(''sudo sh get-docker.sh)
 After the full installation you can then verify using the (''sudo docker run hello-world'') command, which is used as a verification to check if docker is working.

 
__OpenVAS/Greenbone__

Updated the system and install dependencies (which includes the package list)
(''sudo apt update'')

Then comes the installation for the OpenVAS/Greenbone server
('' sudo apt install gvm '') or (''sudo apt install -y gvm'') which accepts all yes or no prompts.

Then after the installation we will now setup the GVM server. 

(''sudo gvm-setup'')

Among these installation steps you should also download the docker compose.yml file that is provided by Greenbone community edition at this link:https://greenbone.github.io/docs/latest/22.4/container/index.html

I will also provide the command I used to install the docker-compose.yml file from them. 
(''curl -f -O -L https://greenbone.github.io/docs/latest/_static/docker-compose.yml --output-dir "$DOWNLOAD_DIR" '')

After installing the docker-compose.yml file we will now run (''docker compose -f docker-compose.yml pull'') and (''docker compose -f docker-compose.yml up -d'')
  the -f docker-compose.yml reads the file and finds out exactly what it needs from the file, more specifically the services it requires from the file.  
  The pull command will pull all the specificed services that were provided within the docker-compose YAML file that being the one linked on the greenbone.github.io page.

Using the command up -d in regards to the docker-compose.yml file is used to create and start the containers that were originally defined in the docker-compose.yml file. 
up --> start the services defined in .yml file
-d --> "detached mode" 


    





