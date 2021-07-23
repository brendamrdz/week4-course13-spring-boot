# DevOps (Developer Operations)


DevOps enables previously isolated roles —development, IT operations, quality engineering, and security— to coordinate and collaborate to create better, more reliable products. By adopting a DevOps culture along with DevOps practices and tools, teams gain the ability to better respond to customer needs, increase trust in the applications they build, and achieve business goals in less time. 
**DevOps is more...**
- **Culture:** Changing the culture in a company, the desire of both teams to collaborate.
- **Automation:** Being able to replicate infrastructure.  Generate a culture in which both developers and operators automate all their tasks.
- **Measurement:** How long the goals of both teams take. Productivity is measured, how long an API request takes, how long it takes an operator to fix an incident in production, everything is measured.
- **Sharing:** Better internal tools shared by both teams so that the code in production is always in high quality and can be fixed as quickly as possible.
With this, the idea is that one of the results is more deployments that contain fewer features and as a consequence, fewer bugs in production.
<img src="https://user-images.githubusercontent.com/26840321/126744266-b472f6cd-e6f0-49b1-a0ff-7d128949f139.png" alt="alt text" width="30%" height="auto">


# What are DevOps tools?
A DevOps tools approach helps developers and operations teams build, test, deploy and monitor applications with speed, quality and control. Successful DevOps software implementations generally rely on an integrated set of solutions, or a toolchain, to eliminate manual steps, reduce errors, increase team agility, and scale beyond small teams.


## Homogeneous Environments for Applications
One of the ways to solve the "it works in my machine" problem is to have homogeneity in all environments. Running code on our local machine should look as similar as possible to the test and production environment.
### Docker
Docker is recommended, it works for all operating systems (WIN10 Pro only) and is reproducible, we can have an infrastructure that shares everything. The images are reproducible, scriptable and the documentation is in the same code.
<img src="https://github.com/brendamrdz/week4-course14-devops/blob/main/images/docker.JPG?raw=true" alt="alt text" width="50%" height="auto">

The following shows how to use a Dockerfile and manage the dependencies to have them in lock in, it is always recommended to install a version that you have already used and tested.

```bashFROM node:11.1.0-alpine
WORKDIR /app
ADD package.json package-lock.json /app/
RUN npm install
EXPOSE 3000
ADD . /app
CMD ["node", "index"]
```
- **FROM**: I look for a source image and from there the container is mounted.
- **WORKDIR**: It is recommended not to run all the root. With this we tell Docker which is going to be our working folder.
- **ADD**: It is where we indicate our dependencies as package.json, it makes cache of that layer not to execute it every time we run our container. It also serves to copy, as we do it in the tenth line.
- **RUN**: we tell docker to execute a command. In this case npm install
- **EXPOSE**: We expose port 3000.
- **CMD**: Here we tell Docker to execute this command when running our container. In this case it will run the application.
- **dockerignore**: it is almost the same as gitignore, but for docker.}

### Terraform
It is possible to make infrastructure with code. To have the equivalent of docker in infrastructure, having the same configuration in different servers and regions, there are several options to do this and one of them is Terraform.
Terraform allows us to write infrastructure as code using declarative configuration files that can run on AWS in several regions and mount the same infrastructure in all of them. We only have to pass the parameters and this will allow us to scale our applications.

## Test Implementation

<img src="https://github.com/brendamrdz/week4-course14-devops/blob/main/images/terraform.JPG?raw=true" alt="alt text" width="40%" height="auto">


https://azure.microsoft.com/es-es/overview/what-is-devops/
https://www.ibm.com/mx-es/cloud/devops
