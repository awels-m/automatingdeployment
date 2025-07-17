# automatingdeployment
here i will be submitting my project on automating deployment on E-Commence website


## PROJECT GOAL
Set up a CI/CD pipeline using Jenkins to build, test, dockerize, and deploy a sample web application — while documenting everything and ensuring security.

⸻

## PROJECT CHECKLIST

I will be completing 5 main stages:
	1.	Jenkins Server Setup
	2.	Source Code Management Integration (e.g. GitHub)
	3.	Jenkins Freestyle Jobs
	4.	Jenkins Pipeline for the App
	5.	Docker Image Creation + Registry Push

Let’s go step by step.

## STEP 1 - INSTALL JENKINS AND CONFIGURE IT
1. Update packages 
   this is done by running this command "sudo apt update" and "sudo apt update -y" on my terminal and the image below depicts this
   ![1img](./1img.png)
   ![2img](./2img.png)
   ![3img](./3img.png)
   
2. Install Java 
   this is done by running this command "sudo apt install openjdk-11-jdk -y"
   the image below depicts this ansd it has been successfully installed
   ![4img](./4img.png)

3. Add Jenkins repo key and source
   this is done by running this command "wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb https://pkg.jenkins.io/debian binary/ > /etc/apt/sources.list.d/jenkins.list'

the image below depicts this 
![5img](./5img.png)

4. Install Jenkins
   this is done by running these commands "sudo apt update" and "sudo apt install jenkins -y"
   the images below depicts this
   ![6img](./6img.png)
   ![7img](./7img.png)

5. Start Jenkins
   this is done by running these command "sudo systemctl start jenkins" and "sudo systemctl enable jenkins". the images below depicts this.
   ![8img](./8img.png)
 

6. Check status
   this is done by running this command "sudo systemctl status jenkins". the image below depicts this.
     ![9img](./9img.png)

## Access Jenkins
this is done by running this on my browser "http://localhost:8080"

the image below depicts this 
![10img](./10img.png)

## INTEGRATE JENKINS WITH GITHUB
Goal: Connect Jenkins to GitHub for automatic build triggering

### Install Git plugin:
the image below depicts that Git Plugins has been successfully installed 
![11img](./11img.png)

Go to Manage Jenkins > Plugins > Available → Search & install “Git Plugin” (if not already installed)
![11img](./11img.png)


### Create a GitHub Repo:
the image below depicts that i have created a new github repository. 
![12img](./12img.png)
![13img](./13img.png)
![14img](./14img.png)


## Setup Webhook in GitHub:

Go to GitHub repo, Settings. then to the  Webhooks, i went aheas to Add webhook. the images below depicts this 
![19img](./19img.png)
![20img](./20img.png)
![21img](./21img.png)
![22img](./22img.png)
## Jenkins Freestyle Jobs
![15img](./15img.png)
![16img](./16img.png)

## CONFIGURE MY FREESTYLE JOB
on tvhe source code management, i selected git and pasted my repository link  and then on the build, i added build steps and then selected execute shell with this command "echo "Building the application..."
cat index.html" i went ahead to save my configuration and manually triggered build. the image below depicts these: 
![23img](./23img.png)
![24img](./24img.png)
![25img](./25img.png)

## ADD JENKINS PIPELINE FOR WEB APPLICATION
IN my github repository root, i created a jenkins file  and added this content into the file as seen in the images below. 
![26img](./26img.png)
![27img](./27img.png)
![28img](./28img.png)
![29img](./29img.png)

i went ahead to add the changes and commited the changes as well as push the changes to the main branch. 

## CREATE PIPELINE JOB IN JENKINS
i created a new item and named it "pipelin-job" and then selected pipeline and under the pipeline settings, 
Select: "Pipeline script from SCM"

SCM: Git

Repository URL: your GitHub URL

Script Path: Jenkinsfile

Save and manually trigger to test.

the images below depicts these.





Push your web app code to a public/private GitHub repo.

In Jenkins:
	1.	Create a new Freestyle job
	the image below depicts this 

![18img](./18img.png)


	2.	In “Source Code Management”, select Git

	3.	Paste the GitHub URL
	4.	Add credentials if needed (for private repos)
