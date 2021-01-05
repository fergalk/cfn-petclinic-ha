# cfn-petclinic-ha
Deploys HA spring-petclinic application on AWS CloudFormation. 

## Stack
- Frontends: nginx & [spring-petclinic-angular](https://github.com/spring-petclinic/spring-petclinic-angular)
- Backends: [spring-petclinic-rest](https://github.com/spring-petclinic/spring-petclinic-rest)
- Database: Aurora PostgreSQL

## Backend
Service petclinic-backend.service runs petclinic backend server. Content is stored in /apps/petclinic-backend. The server listens on 9966.

## Frontend
The frontend web content is served by nginx. The content is stored in /apps/petclinic-frontend.