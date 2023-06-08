# Research Document: CI/CD Implementation in Project
![image](https://github.com/Arthur-Brouwers/ArthurBrouwers/assets/124791770/6f266373-c312-44c6-b458-92233333b7c2)

## Definition: Continuous Integration/Continuous Delivery (CI/CD)
Continuous Integration/Continuous Delivery (CI/CD) is a set of practices that enable software development teams to deliver code changes frequently and reliably. It involves integrating code changes into a shared repository multiple times a day and automating the build, test, and deployment processes.

## Overview
In our project, we implemented CI/CD practices to ensure efficient and reliable software development. We utilized Continuous Integration (CI) to integrate code changes and perform automated tests, and Continuous Delivery (CD) to automate the deployment of builds to staging or production environments.

## Continuous Integration
Continuous Integration (CI) is a software development practice that emphasizes frequent integration of code changes into a shared repository. It enables early detection of errors and facilitates efficient collaboration among team members.

### Implementation in our Project
To implement Continuous Integration in our project, we followed these steps:

1. **Feature Branches**: We created separate branches for each new feature or code change.
2. **Pull Requests**: When a feature was complete, we initiated a pull request to merge the branch into the "main" branch.
3. **CI Pipeline**: We configured a CI pipeline (`test.yml`) that triggered upon pull request creation. The pipeline built the project, installed necessary packages, and executed integration and unit tests. We leveraged SonarCloud for automated code scanning to ensure code quality.
4. **Code Review**: We enforced a mandatory code review by another team member before merging the pull request into the "main" branch.

By following these steps, we ensured that code changes were regularly integrated, tested, and reviewed, thereby maintaining code quality and early error detection.

## Continuous Delivery
Continuous Delivery (CD) extends the concept of CI by automating the deployment of builds to staging or production environments. It aims to enable a constant flow of changes into production through automated deployments.

### Implementation in our Project
To implement Continuous Delivery in our project, we employed Docker as a containerization technology. Here's how it was done:

1. **Successful CI Pipeline**: Upon successful completion of the CI pipeline and merging into the "main" branch, the code was ready for deployment.
2. **CD Pipeline**: Our CD pipeline (`DockerImage.yml`) was triggered, starting with checking out the code and logging into our DockerHub account using repository secrets.
3. **Docker Image Build**: The pipeline built the Docker image based on the Dockerfile, which specified the image's configuration, dependencies, and runtime commands.
4. **Image Push**: The built image was pushed to our DockerHub repository with the specified tag, allowing easy access for deployment.

Utilizing Docker allowed us to create self-contained and reproducible containers, ensuring consistency and ease of deployment across different environments.

### Dockerfile
A Dockerfile is a text file that contains instructions for building a Docker image. It defines the desired state of the container and automates the build process. The Dockerfile specifies the base image, copies files, configures the environment, installs dependencies, and defines commands to run within the container.

### Challenges
During our implementation, we encountered a few challenges that required troubleshooting and adjustments:

- **Front-End**: We faced issues with running the Docker container for the front-end. After investigation, we realized that the development-specific command `npm run dev` couldn't be used in a production environment. We modified our Dockerfile to use `npm run serve` instead.
- **API**: We encountered issues with the API...
