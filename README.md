# Credit Score Navigator

---

## Introduction

The Credit Score Analysis Tool automates the process of credit score evaluation by integrating data from various sources including credit bureaus and banking transaction records. The tool provides real-time credit scoring, predictive analytics based on customer behavior, and detailed reporting features for bank staff. The project leverages a microservices architecture to ensure scalability and efficient management of different service components.

## Project Architecture

### 1. Client Side
- **Frontend**: Angular 10
- **Team**: Dedicated frontend developers team

### 2. API Gateway
- **Technology**: Spring Cloud Gateway
- **Functionality**: Single-entry point for all client requests, handling routing, authentication, and logging.

### 3. Microservices
- **Data Collection Service**: Manages ingestion and preprocessing of financial data.
- **Credit Scoring Service**: Calculates credit scores using predefined algorithms.
- **User Management Service**: Handles authentication and user account management.
- **Report Service**: Generates detailed credit reports and analytics.

### 4. Database
- **Technology**: MySQL (planned migration to MongoDB for some services)
- **Caching**: Redis for in-memory caching of frequently accessed data.

### 5. Logging and Monitoring
- **Logging**: Log4j2
- **Monitoring**: Splunk for real-time log analysis and visualization.

### 6. Messaging System
- **Technology**: Kafka for real-time updates and asynchronous communications.

### 7. Security
- **Authentication**: OAuth for secure access control.

### 8. Deployment and Operations
- **Containerization**: Docker
- **Orchestration**: Kubernetes
- **CI/CD**: Jenkins for automated build, test, and deployment processes.

## Project Flow

1. **User Interaction and Authentication**
   - Bank officers log in through the UI.
   - Authentication handled by the User Management Service.
   - Secure sessions managed using OAuth.

2. **Data Collection and Processing**
   - Financial data gathered from internal and external sources.
   - Data validated and preprocessed by the Data Collection Service.

3. **Credit Scoring Calculation**
   - Processed data forwarded to the Credit Scoring Service.
   - Scores calculated using statistical algorithms and machine learning.

4. **Report Generation and Delivery**
   - Detailed credit reports generated by the Report Service.
   - Reports available via the UI and can be emailed to stakeholders.


## Logging with Log4j2

Log4j2 provides powerful logging capabilities, integrated with Splunk for real-time log analysis.

## Redis Cache Utilization

Redis is used for caching frequently accessed data, optimizing performance and reducing database load.

## CI/CD Pipeline

- **Version Control**: Git (hosted on GitLab)
- **Build Automation**: Maven or Gradle
- **Artifact Repository**: Nexus or Artifactory
- **Deployment**: Docker and Kubernetes
- **Continuous Deployment**: Techniques like blue-green deployments or canary releases.

## Data Layer / Schemas

### Major Tables
- **Users Table**: User details and status.
- **Credit Scores Table**: Credit scores and history.
- **Financial Records Table**: Transaction details.
- **Reports Table**: Generated credit reports.
- **Audit Logs Table**: User actions and timestamps.

## REST APIs

### Data Collection Service
- Retrieve, submit, update, and delete financial data.
- Fetch transaction and loan data.

### Credit Scoring Service
- Fetch, calculate, update, and delete credit scores.
- Retrieve score history and provide average scores.

### User Management Service
- Manage user details, authentication, and account status.

### Report Service
- Fetch, generate, update, and delete reports.
- Send reports to specified recipients.

