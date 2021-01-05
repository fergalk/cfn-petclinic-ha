# cfn-petclinic-ha
Deploys HA spring-petclinic application on AWS CloudFormation. 
## Stack
- Frontends: nginx & [spring-petclinic-angular](https://github.com/spring-petclinic/spring-petclinic-angular)
- Backends: [spring-petclinic-rest](https://github.com/spring-petclinic/spring-petclinic-rest)
- Database: Aurora PostgreSQL

## Web access to petclinic UI
The URL for the petclinic web interface is in the outputs section, under `FrontendURL`.

## SSH access
To log onto any of the servers, first SSH onto a bastion host using the SSH key you selected when you built the stack. From there, you can SSH onto any of the servers in the private subnets using the same SSH key (note - you will need to add the private key to the bastion host manually).

## High level architecture
*For the purposes of simplicity, SSH & web access flows are not shown*
![architecture diagram](architecture.png)

## Server config
### Backend
Service petclinic-backend.service runs petclinic backend server. Content is stored in /apps/petclinic-backend. The server listens on TCP 9966.
### Frontend
The frontend web content is served by Nginx. The content is stored in /apps/petclinic-frontend. The server listens on TCP 80.

## Network
### Ports
- Backend API - TCP 9966
- Frontend web server - TCP 80
- PostgreSQL database - 5432