# Provisioning container with Packer and Ansible and automating with Jenkins
**By Antonio Azambuja and Fabio Marsiaj**

In this project we provide a docker image with packer and ansible, configuring it to run a .jar file from a
simple project.

## Summary

  - [Introduction](#introduction)
  - [Requirements](#requirements)
  - [Installation](#installation)
  - [Important Settings](#important-settings)
  - [Running Jenkins](#running-jenkins)
  - [Authors](#authors)
  
  ## Introduction
  
   By HashiCorp: 
   "Packer is an open source tool for creating identical machine images for multiple platforms from a single source configuration."
   Ansible is an open-source software provisioning, configuration management, and application-deployment tool.[2] It runs on many Unix-like systems, and can configure both Unix-like systems as well as Microsoft Windows.
   
   We can use a base docker image and configure it in our way using ansible. And with 
   Jenkins - an automation server - we automate it all.
   Our image is suppose to run a .jar with entrypoint command.

  ## Requirements
  
  - [Git](https://git-scm.com/)
  - [Jenkins](https://jenkins.io/)
  - [JFrog](https://jfrog.com/)
  
  ## Installation
  
 - Install Git:
```
$apt-get install git
```
  
  - Clone the project from github:
```
$git clone https://github.com/antonioazambuja/jts.cloud-native.2019.2/tree/temafinal1
```

  ## Important Settings
  
  - Installing Packer:
```
$sudo apt-get install packer
```

  - Installing Ansible:
```
$sudo apt-get install ansible
```

  - Install docker:
```
$sudo apt-get install docker
```

  - Add Jenkins to Docker Group:
```
$sudo usermod -a -G docker jenkins
```

  - Give access to .docker/ folder on your sistem:
```
$sudo chmod -R 777 .docker/*
```
  
  ## Running Jenkins
    
   When you install Jenkins make sure to install all recommended plugins and also
   artifactory plugin, so that you can run JFrog via pipeline. 
  
   After installing Jenkins, it should be available at http://localhost:8080
   
   Note that you should configure your own ENV_JFROG_USER and ENV_JFROG_PASSWORD
   at: Manage Jenkins>System Configuration
   and at Global Properties mark up "enviroment variables" and then set it.
   
   **Also, at /tasks/infra/variables.json you should set your own dockerhub credentials.**
  
   Check out our video about the project at:
   https://youtu.be/NbkTU-Gw8FU
  
   ## Authors
   
   
   **Antonio Marcos Silva de Azambuja** -  [GitHub](https://github.com/antonioazambuja)
   
   <a href="https://github.com/fabioqmarsiaj">
        <img 
        alt="Imagem do Autor Fabio Marsiaj" src="https://avatars3.githubusercontent.com/u/45765571?s=460&v=4
" width="100">
   </a>
   
   **Fabio Quinto Marsiaj** -  [GitHub](https://github.com/fabioqmarsiaj)
   
   <a href="https://github.com/fabioqmarsiaj">
        <img 
        alt="Imagem do Autor Fabio Marsiaj" src="https://avatars0.githubusercontent.com/u/34289167?s=460&v=4" width="100">
  </a>
  
