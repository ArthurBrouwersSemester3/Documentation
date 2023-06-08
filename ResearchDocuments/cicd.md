# What is CI/CD?
> Continuous Integration/Continuous Delivery (CI/CD) is a set of practices that help software development teams deliver code changes more frequently and reliably. [infoworld](https://www.infoworld.com/article/3271126/what-is-cicd-continuous-integration-and-continuous-delivery-explained.html)

![image](https://github.com/Arthur-Brouwers/ArthurBrouwers/assets/124791770/6f266373-c312-44c6-b458-92233333b7c2)

## Continuous Intergration
Continuous Integration (CI) is a software development practice that requires developers to integrate code into a shared repository several times a day. Each check-in is then verified by an automated build, allowing teams to detect problems early. By integrating regularly, you can detect errors quickly and locate them more easily.

### How did we inmplement Continuous Improvement in our project?
To make use of continous improvement, we created new branches for each new feature. When we finished the new feature, we can make a pull request to merge the branch into "main".

Once the pull request has been made, it will trigger our [CI pipeline](https://github.com/ArthurBrouwersSemester3/Front-end/blob/main/.github/workflows/test.yml). Our CI pipeline will build the project and install all necessary packages to run the integration- and unit tests. it will also make sure to run these tests and check if they all pass. We have used a new feature of sonarcloud the automated scan which means on every pull request you make to main it will automatically scan the project for code smells, bugs and more. if both check succeeds you are able to merge the feature branch into main , If either one of the tests fails or the SonarCloud fails, merging is blocked. We use the standard standards for sonarcloud which means an A rating on all the 5 checks we did this because our project isn't to big so there shouldn't be code smells or bugs in it. However if this project would grow we would have to reconsider these choises.

Additionally, since we are working together on the project, We have forced that the other person needs to add a code review and approve the merge. 

After all these steps are successful, you are able to merge into main. and u will continue to our cd pipeline

## Continuous Delivery
Continuous Delivery (CD) is an extension of Continuous Integration where automated builds are deployed to a staging or production environment. The goal of Continuous Delivery is to enable a constant flow of changes into production via automated deployments.
 
### How did we inmplement Continuous Devivery in our project?
To make use of Continuous delivery, we made use of Docker. If all the previous steps in the ci pipeline succeeded and you merged the pull request it will push the code into main where our cd pipelin egets triggered, our [CD pipeline](https://github.com/ArthurBrouwersSemester3/Front-end/blob/main/.github/workflows/DockerImage.yml) this pipeline starts of checking out all the code and logging into our dockerhub account so it can access the repository we have declared the login credentials in our repository secrets. then it will build the image and push it into the repository with the tag we have declared which is front-end for the front-end and back-end for the back-end.

###Dockerfile
A Dockerfile is a text file that contains instructions to build a Docker image. It is used as a blueprint for creating self-sufficient containers. Docker images are created from Dockerfiles using the docker build command.

The Dockerfile consists of a series of instructions that specify the base image, copy files into the image, configure the environment, install dependencies, and define the commands to run when the container starts. It allows you to define the desired state of the container and automate the build process.

###struggles 
we came along some issues in the front-end, we coudn't run our docker container even tho the ports were bound correctly so after some time we found out npm run dev is for development stage and can't be used in a production stage this mean't we had to change our dockerfile to npm run serve instead of npm run dev.

In our API we had the issue that the jar file didn't rebuild when making the image so we would have to clean and install manually every time before merging, it is important that our .jar file is up to date. In that case, we integrated a rebuild in our [API CD pipeline](https://github.com/ArthurBrouwersSemester3/API/blob/main/.github/workflows/Docker-Build-Push.yml) instead of doing it manually. We also had the issue that gitignore ignores the jar file which would also lead to errors.
