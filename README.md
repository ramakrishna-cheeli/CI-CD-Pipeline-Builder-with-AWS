# CI-CD-Pipeline-Builder-with-AWS
## Project Overview
- To build the Microservices and Continous Integration and Continous Development(CI/CD), in this project at least 15 AWS Services are used.
- The KeyObjectives are
  - Recognize how a Node.js web application is coded and deployed to run and connect to a relational database where the application data is stored.
  - Create an AWS Cloud9 integrated development environment (IDE) and a code repository (repo) in which to store the application code.
  - Split the functionality of a monolithic application into separate containerized microservices.
  - Use a container registry to store and version control containerized microservice Docker images.
  - Create code repositories to store microservice source code and CI/CD deployment assets.
  - Create a serverless cluster to fulfill cost optimization and scalability solution requirements.
  - Configure an Application Load Balancer and multiple target groups to route traffic between microservices.
  - Create a code pipeline to deploy microservices containers to a blue/green cluster deployment.
  - Use the code pipeline and code repository for CI/CD by iterating on the application design.
## Need of the Project
- The application currently runs as a monolithic application. It has reliability and performance issues. As a Software Development Engineer or Application Developer or Cloud Support  Engineer your task is to split the monolithic application into microservices, so that you can scale the services independently and allocate more compute resources to the services that experience the highest demand, with the goal of avoiding bottlenecks.
- A microservices design will also help avoid single points of failure, which could bring down the entire application in a monolithic design. With services isolated from one another, if one microservice becomes temporarily unavailable, the other microservices might remain available.
## Requirements
- The solution must meet the following requirements:
  - R1 - Design: The solution must have an architecture diagram.
  - R2 - Cost optimized: The solution must include a cost estimate.
  - R3 - Microservices-based architecture: Ensure that the solution is functional and deploys a microservice-based architecture.
  - R4 - Portability: The solution must be portable so that the application code isn't tied to running on a specific host machine.
  - R5 - Scalability/resilience: The solution must provide the ability to increase the amount of compute resources that are dedicated to serving requests as usage patterns change, and   the solution must use routing logic that is reliable and scalable.
  - R6 - Automated CI/CD: The solution must provide a CI/CD pipeline that can be automatically invoked when code is updated and pushed to a version-controlled code repository.
## Project Phases
| Phase | Detail | Requirement |
| ----- | ------ | ----------- |
| 1     | Create an architecture diagram and cost estimate for the solution. | R1, R2 |
| 2     | Analyze the design of the monolithic application and test the application. | R3 |
| 3     | Create a development environment on AWS Cloud9, and check the monolithic source code into CodeCommit. | R3 |
| 4     | Break the monolithic design into microservices, and launch test Docker containers.  | R3, R4 |
| 5     | Create ECR repositories to store Docker images. Create an ECS cluster, ECS task definitions, and CodeDeploy application specification files. | R3 |
| 6     | Create target groups and an Application Load Balancer that routes web traffic to them.  | R5 |
| 7     | Create ECS services.	     | R5 |
| 8     | Configure applications and deployments groups in CodeDeploy, and create two CI/CD pipelines by using CodePipeline.  | R5, R6 |
| 9     | Modify your microservices and scale capacity, and use the pipelines that you created to deploy iterative improvements to production by using a blue/green deployment strategy. | R5, R6 |

## Phase 1: Planning the design and estimating cost
- In thiis Phase need to create the architecture diagram and estimate the cost.
-  An important first step for any solution is to plan the design and estimate the cost. Review the various components in the architecture to adjust the estimated cost. Cost, along with the features and limitations of specific AWS services, is an important factor when you build a solution.
-  **Task 1.1: Create an architecture diagram**
  - Read through the phases in this document to be aware of which AWS services and features you have been asked to use. Be sure to include the following services or resources in your diagram:
      - Amazon Virtual Private Cloud (Amazon VPC)
      - Amazon EC2: Instances, Application Load Balancer, target groups
      - AWS CodeCommit: Repository
      - AWS CodeDeploy
      - AWS CodePipeline: Pipeline
      - Amazon Elastic Container Service (Amazon ECS): Services, containers, tasks
      - Amazon Elastic Container Registry (Amazon ECR): Repository
      - AWS Cloud9 environment
      - AWS Identity and Access Management (IAM): Roles
      - Amazon Relational Database Service (Amazon RDS)
      - Amazon CloudWatch: Logs
      - Refernces
          - [Architecture Icons](https://aws.amazon.com/architecture/icons/)
          - [Architecture Diagram](https://aws.amazon.com/architecture/reference-architecture-diagrams/?solutions-all.sort-by=item.additionalFields.sortDate&solutions-all.sort-order=desc&whitepapers-main.sort-by=item.additionalFields.sortDate&whitepapers-main.sort-order=desc&awsf.whitepapers-tech-category=*all&awsf.whitepapers-industries=*all)
- **Task 1.2: Develop a cost estimate**
- Develop a cost estimate that shows the cost to run the solution that you created an architecture diagram for. Assume that the solution will run in the us-east-1 Region for 12 months.
- [AWS Pricing Calculator](https://calculator.aws/#/)
## Phase 2: Analyzing the infrastructure of the monolithic application
- Analyze the current application infrastructure and then test the web application.
- **Task 2.1: Verify that the monolithic application is available**
   - Verify that the monolithic web application is accessible from the internet
       - Navigate to the Amazon EC2 console
       - Copy the Public IPv4 address of the MonolithicAppServer instance, and load it in a new browser tab, website displays.
       - The page is available at http:// instead of https://. Your browser might indicate that the site isn't secure because it doesn't have a valid SSL/TLS certificate. You can ignore the warning in this development environment.
       - 
  
