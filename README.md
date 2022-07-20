Video: https://youtu.be/VBI7KAQdOz0

# Explanation

- ### The first pipeline tests the application, builds a jar and uploads it to jfrog artifactory.

- ### The second pipeline downloads the jar from jfrog artifactory, builds a docker image with jar inside, provisions the image using Ansible to install the jdk, and uploads that image to dockerhub.

- ### The third pipeline downloads from dockerhub the image and runs it with docker.

# 1- Installations

### 1.1- Install jenkins following the recommendations of the official website:

https://www.jenkins.io/doc/book/installing/linux/

### 1.2- Install JFROG following the documentation:

https://www.jfrog.com/confluence/display/JFROG/Installing+Artifactory

### 1.3- Install Packer on your machine following the documentation:

https://learn.hashicorp.com/tutorials/packer/get-started-install-cli

# 2- Preparation

### 2.1- Create an account on the official jfrog website:

https://jfrog.com/start-free/

### 2.2- Sign in JFrog Artifactory and create a repository.

### 2.3- By default, jenkins is connected to port 8080 on your machine, access it through the link:

http://localhost:8080/

### 2.4- Create a username and password, check the option to install the recommended plugins.

### 2.5- Fork the following repository:

https://github.com/YagoJanos/TemaFinal1Configs

### 2.6- Modify the JenkinsFile files to suit your JFROG repository:

![image](https://user-images.githubusercontent.com/73187867/178352226-17161525-4ea6-40ba-a159-1aecee86aa49.png)

### 2.7- Modify the Packer file to upload the container image to your dockerhub repository:

![image](https://user-images.githubusercontent.com/73187867/178352518-070b491a-75ac-42ec-a1f8-b0d182233682.png)

### 2.8- Configure your credentials in jenkins with the passwords needed to run the pipeline.

# 3- Execution

### 3.1- Click on new item:

![image](https://user-images.githubusercontent.com/73187867/178350005-c6798498-0ea0-4134-96c1-e493faa0f297.png)

### 3.2- Enter a name for your pipeline

![image](https://user-images.githubusercontent.com/73187867/178350251-c659ab8a-3f37-4ed1-86c7-0bb0391bb825.png)

### 3.3- Click on pipeline:

![image](https://user-images.githubusercontent.com/73187867/178350117-12e99d1a-a41b-460c-9455-2ebc51820dc9.png)

### 3.4- For the three pipelines, go down the page and put the following configuration:

![image](https://user-images.githubusercontent.com/73187867/178350686-f1387eec-bc6e-43c9-a91b-ddb0824ea234.png)

### 3.5- For Job1, fill in the Script Path field as follows:

![image](https://user-images.githubusercontent.com/73187867/178351009-a97ef4a9-d000-4110-90e5-cd814a1929da.png)

### 3.6- For Job2, fill in the Script Path field as follows:

![image](https://user-images.githubusercontent.com/73187867/178351084-6d90aab2-a23e-4e2a-919b-6ea50378baae.png)

### 3.7- For Job3, fill in the Script Path field as follows:

![image](https://user-images.githubusercontent.com/73187867/178350915-21199aea-153d-4d2e-8b04-6c9983c1158d.png)

### 3.7- Go back to the Dashboard and run the pipelines in order.
