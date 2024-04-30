# CloudNative Web Application  
[![GCP](https://img.shields.io/badge/GCP-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white)](https://cloud.google.com/)
[![Terraform](https://img.shields.io/badge/Terraform-623CE4?style=for-the-badge&logo=terraform&logoColor=white)](https://www.terraform.io/)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Packer](https://img.shields.io/badge/Packer-02A8EF?style=for-the-badge&logo=packer&logoColor=white)](https://www.packer.io/)
[![Google Cloud Functions](https://img.shields.io/badge/Google_Cloud_Functions-FF6F00?style=for-the-badge&logo=google-cloud&logoColor=white)](https://cloud.google.com/functions)
[![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)](https://github.com/features/actions)
[![Mailgun](https://img.shields.io/badge/Mailgun-F06A6A?style=for-the-badge&logo=mailgun&logoColor=white)](https://www.mailgun.com/)  

## Overview  
Welcome to the CloudOps ecosystem! This suite contains an integrated set of repositories designed to automate the deployment of a secure, scalable, and highly available web application on Google Cloud Platform (GCP). Utilizing Terraform for infrastructure automation, Google Cloud Functions for serverless operations, and Spring Boot for backend development, this project delivers a comprehensive strategy for deploying and managing modern, cloud-native applications with efficiency and resilience.

![CloudNative Web Application](https://raw.githubusercontent.com/csye6225-eashan-roy/.github/main/profile/Cloud%20Native%20WebApp.webp)

## Architecture Overview


![Architecture Diagram](link-to-diagram-image)

## Key Features  

- **Spring Boot RESTful APIs**: Engineered with Spring Boot, the application's backend architecture delivers a suite of RESTful APIs enabling comprehensive user management, including registration, profile retrieval, updates, and database health checks. The robust API suite enforces secure access through Basic HTTP authentication and Base64 header encoding, ensuring that sensitive credentials are transmitted securely. User passwords are safeguarded in a PostgreSQL database employing the Bcrypt hashing algorithm with a unique salt for each password, significantly enhancing data protection and privacy.  

- **Automated GCP Infrastructure**: Leverages Infrastructure-as-code (IaC) tool Terraform for infrastructure provisioning and automation in Google Cloud platform to establish a repeatable and secure cloud environment. This includes VPC, subnets, routes, firewalls, compute engine (VM), cloud SQL (postgres database), cloud storage, cloud functions (serverless), application load balancer, cloud DNS, Google managed SSL certificate, and encryption keys.  

- **Immutable Server Deployments**: Utilizes Packer within a GitHub Actions workflow to craft robust machine images pre-equipped with pre-built and tested application artifacts. This method encapsulates not only the application's runtime environment but also its comprehensive test suites, ensuring code integrity. The resulting immutable images, once provisioned by Terraform, yield ready-to-serve virtual machines that preclude the necessity for manual SSH configurations. The deployment process is further automated through VM startup scripts that automatically configure database connections and kick-start the application. This strategy is the embodiment of the immutable server paradigm, where servers are redeployed rather than directly altered, enhancing consistency and reliability across the delivery pipeline.  

- **CI/CD with GitHub Actions**: Constructs a continuous integration and delivery pipeline using GitHub Actions, automating the testing and deployment process.    

- **Event-Driven User Verification**: Employs an event-driven architecture that fortifies user validation via email verification, a critical step that markedly enhances user engagement. Utilizing Google Pub/Sub, this mechanism automatically dispatches a unique verification link to a user's email upon account creation. The serverless Cloud Function, triggered by the Pub/Sub event, collaborates with Cloud SQL to append a time-sensitive UUID token to the user’s profile. The verification email, powered by Mailgun's robust email delivery service, contains a link with the token, which upon clicking within the stipulated five-minute window, confirms the user’s authenticity through a REST API endpoint. This secure handshake not only confirms the user's credentials but also activates their ability to utilize further API services, thereby reinforcing a secure and user-friendly registration process.  

- **Application Logging and Metrics**: Enhances diagnostic capabilities of application through structured JSON logging, with log data streamed to Google Cloud Observability.  

- **Scalability and Security**: Leverages dynamic scaling, load balancing, security groups, IAM roles, and customer managed encryption keys to ensure application scalability and security.  


## Repositories  

- [**WebApp**](https://github.com/csye6225-eashan-roy/webapp): Spring Boot-based RESTful service for user management with PostgreSQL.

- [**Terraform Infrastructure (tf-gcp-infra)**](https://github.com/csye6225-eashan-roy/tf-gcp-infra): Terraform code to provision and manage the GCP infrastructure.

- [**Serverless**](https://github.com/csye6225-eashan-roy/serverless): Google Cloud Functions for event-driven processes like email verification.

  

[//]: # (## Getting Started)

[//]: # (To utilize this suite, follow the setup instructions in the README of each repository.)

## Use Cases
- Automated cloud deployments
- Accelerated autoscaling and consistent infra with Packer golden images  
- Event-driven serverless workflows
- Infrastructure as code for GCP

To gain more insights on this project and its capabilities, please refer to their respective repositories. We encourage contributions and feedback on all aspects of the suite. If you wish to contribute, please reach out to the project maintainers :)
