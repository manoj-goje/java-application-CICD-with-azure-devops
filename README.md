# java-application-CICD-with-azure-devops# Java Application Deployment on Azure VM Using Azure DevOps

## Project Overview
This project demonstrates automated CI/CD deployment of a Java application on an Azure Linux Virtual Machine using Azure DevOps.

## Architecture
Developer → GitHub → Azure DevOps Pipeline → Maven Build → JAR Artifact → Azure Linux VM → Java Application

## Technologies Used
- Microsoft Azure
- Azure DevOps
- Azure Virtual Machine (Ubuntu)
- Java 17
- Maven
- Git and GitHub
- YAML
- SSH
- Linux

## CI Pipeline
1. Trigger pipeline when code is pushed to the main branch.
2. Compile Java application using Maven.
3. Execute unit tests.
4. Generate executable JAR file.
5. Publish JAR as a pipeline artifact.

## CD Pipeline
1. Download the published JAR artifact.
2. Connect to Azure VM using SSH.
3. Copy the JAR file to the VM.
4. Restart the Java application using systemd.
5. Verify application service status.

## Deployment Prerequisites
- Azure DevOps project.
- Azure Linux VM.
- Java 17 runtime installed.
- Maven-based Java application.
- SSH service connection configured in Azure DevOps.
- Required network and VM permissions.

## Deployment Verification
Check application status:

```bash
sudo systemctl status myjavaapp
```

View application logs:

```bash
sudo journalctl -u myjavaapp -f
```

Access application:

```text
http://YOUR-VM-PUBLIC-IP:8080
```

## Project Outcome
Automated the build and deployment process of a Java application on Azure VM using an Azure DevOps YAML pipeline.
