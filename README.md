# DevOps (Developer Operations)
DevOps enables previously isolated roles —development, IT operations, quality engineering, and security— to coordinate and collaborate to create better, more reliable products. By adopting a DevOps culture along with DevOps practices and tools, teams gain the ability to better respond to customer needs, increase trust in the applications they build, and achieve business goals in less time. 


**DevOps is more...**
- **Culture:** Changing the culture in a company, the desire of both teams to collaborate.
- **Automation:** Being able to replicate infrastructure.  Generate a culture in which both developers and operators automate all their tasks.
- **Measurement:** How long the goals of both teams take. Productivity is measured, how long an API request takes, how long it takes an operator to fix an incident in production, everything is measured.
- **Sharing:** Better internal tools shared by both teams so that the code in production is always in high quality and can be fixed as quickly as possible.
With this, the idea is that one of the results is more deployments that contain fewer features and as a consequence, fewer bugs in production.
<br><br><img src="https://user-images.githubusercontent.com/26840321/126744266-b472f6cd-e6f0-49b1-a0ff-7d128949f139.png" alt="alt text" width="30%" height="auto"><br><br>
## DevOps lifecycle phases
# What are DevOps tools?
A DevOps tools approach helps developers and operations teams build, test, deploy and monitor applications with speed, quality and control. Successful DevOps software implementations generally rely on an integrated set of solutions, or a toolchain, to eliminate manual steps, reduce errors, increase team agility, and scale beyond small teams.
<br><br><img src="https://github.com/brendamrdz/week4-course14-devops/blob/main/images/Diagrama-DevSecOps-1024x572.png?raw=true" alt="alt text" width="100%" height="auto"><br><br>
## Homogeneous Environments for Applications
One of the ways to solve the "it works on my machine" problem is to have homogeneity in all environments. Running code on our local machine should look as similar as possible to the test and production environment.
### Docker
Docker is recommended, it works for all operating systems (WIN10 Pro only) and is reproducible, we can have an infrastructure that shares everything. The images are reproducible, scriptable and the documentation is in the same code.
The following shows how to use a Dockerfile and manage the dependencies, it is always recommended to install a version that you have already used and tested.
```bashFROM node:11.1.0-alpin
WORKDIR /app
ADD package.json package-lock.json /app/
RUN npm install
EXPOSE 3000
ADD . /app
CMD ["node", "index"]
```
- **FROM**: It looks for a source image and from there the container is mounted.
- **WORKDIR**: It is recommended not to run all the root. With this we tell Docker which is going to be our working folder.
- **ADD**: It is where we indicate our dependencies as package.json, it makes cache of that layer not to execute it every time we run our container.
- **RUN**: It tells docker to execute a command. In this case npm install.
- **EXPOSE**: We expose port 3000.
- **CMD**: Here we tell Docker to execute this command when running our container. In this case it will run the application.
- **dockerignore**: it is almost the same as gitignore, but for docker.}

### Terraform
It is possible to make infrastructure with code. To have the equivalent of docker in infrastructure, having the same configuration in different servers and regions, there are several options to do this and one of them is Terraform.
Terraform allows us to write infrastructure as code using declarative configuration files that can run on AWS in several regions and mount the same infrastructure in all of them. We only have to pass the parameters and this will allow us to scale our applications.

## Continous Deployments
We have different ways to get our code to production, there is Continuous Delivery and Continuous Deployment, but of course we can also do it by hand. The latter is not what we want.


The difference between Continuous Delivery and Continuous Deployment is quite simple, it's the same process, but in Continuous Deployment it is sent to production automatically based on the results of our acceptance tests and in Continuous Delivery we can do it by hand.


Neither is better than the other, it all depends on what you are doing at the moment and the things you are taking to production. If it is something critical and there is no safety you can do it manually.


The ultimate concept is to release to production more frequently and with fewer errors, the way it is implemented is a detail. The result should always be fewer bugs.
There are several types of Deployments:
- **Blue/Green:** Have two tags of the same code giving update to one of them while the other serves the traffic.
- **Canary:** This can be used in conjunction with other types. We have a node pull and we are going to implement something new and it can be risky. We only modify one of those nodes.
- **Rolling:** It is to update machines one by one. They are safe since we can monitor the progress.
https://azure.microsoft.com/es-es/overview/what-is-devops/
https://www.ibm.com/mx-es/cloud/devops
