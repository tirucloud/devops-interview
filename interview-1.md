## interview-1- cloud/devops engineer role


### 1. How do you decide the number of target groups to configure for an Application Load Balancer?
```
The number of target groups behind an Application Load Balancer is decided based on application
architecture and service separation.
Each independently deployable or scalable component, such as a microservice,
typically gets its own target group.
Different routing rules, ports, or health check requirements also require separate target groups.
Deployment strategies like blue-green or canary deployments increase the number of target groups.
There is no fixed limit; the goal is clean isolation, scalability, and safe deployments.
```

### 2. How many target groups are typically configured behind an Application Load Balancer?
```
There is no fixed number of target groups behind an Application Load Balancer; it depends on the application design and number of services.
In practice, small applications use 1–2 target groups, while microservices-based production systems commonly use 5–20 target groups.
Large enterprise environments can have dozens of target groups behind a single ALB, driven by routing rules and
deployment strategies like blue-green or canary.
```
### 3. Can you explain the end-to-end flow of a user request, starting from accessing an application URL to how the request reaches and interacts with the database?
```bash
user -- url -- aplb -- traget group -- front end --- backend -- DB
```
### 4. How would you implement user-specific access control for S3 objects in a production environment?
```
This is a very common senior-level question.

✅ Best Practice Architecture
🔐 Option 1: IAM + Pre-Signed URLs (Most common)

Users authenticate (Cognito / Auth service)

Backend generates pre-signed URL

User accesses only their object

URL expires automatically

✔️ Secure
✔️ No public access
✔️ Works well for downloads/uploads
```
### 5. Are you using api gateway in architeccture or alb?
```bash
 we are using API Gateway and Application Load Balancer.
```
### 6. How do you perform Linux server patching in a production environment while minimizing downtime and risk?
```
In production, we perform Linux patching using rolling updates, removing one server at a time from the load balancer to avoid downtime.
We apply security-first patches, reboot only when required, and validate application health before adding the server back.
Risk is minimized using snapshots or immutable AMI-based deployments with a clear rollback plan.
```
### 7. In your experience, what has been the maximum application downtime, and how was it handled?
```bash

“In my experience, the maximum application downtime was around 20–25 minutes
during a production incident.”

What happened:

“It was caused by a failed deployment combined with an unexpected dependency issue,
which led to application pods becoming unhealthy.”

How it was handled:

Alerts were triggered via monitoring within a few minutes

Traffic was immediately shifted back using rollback / previous stable version

The issue was isolated using logs and health checks

Service was restored within the defined RTO

Post-incident actions:

Added pre-deployment validation and canary deployment

Improved health checks and readiness probes

Added automated rollback in the CI/CD pipeline

Documented the incident with a post-mortem

Result:

“Since implementing these changes, we’ve avoided similar outages and reduced
deployment-related risk significantly.”
```
### 8. Can you walk us through a sample Jenkins pipeline that you implemented in your project?
```bash
@Library('Shared') _

pipeline {
    agent any
    
    environment {
        // Update the main app image name to match the deployment file
        DOCKER_IMAGE_NAME = ''
        DOCKER_MIGRATION_IMAGE_NAME = ''
        DOCKER_IMAGE_TAG = "${BUILD_NUMBER}"
        GITHUB_CREDENTIALS = credentials('github-credentials')
        GIT_BRANCH = "master"
    }
    
    stages {
        stage('Cleanup Workspace') {
            steps {
                script {
                    clean_ws()
                }
            }
        }
        
        stage('Clone Repository') {
            steps {
                script {
                    clone("https://github.com/.........","master")
                }
            }
        }
}
```
### 10. why are you using multiple tools for monitoring (elk, prometheus and grafana)?
```bash
Using ELK, Prometheus, and Grafana together gives us full observability—metrics for detection, logs for diagnosis,
and dashboards for visibility.Because no single tool covers logs, metrics, a
nd visualization end-to-end. Each tool solves a different observability problem.
```
### 11. what is crontab? how to schedule a job in linux?
```bash
Crontab is a Linux scheduler used to run commands or scripts automatically at a specified time or interval (minutes, hours, daily, weekly, etc.).
```
### 12. can you write shell script and python script for automation?
### 13. can you install and setup jenkins from the scratch?
### 14. How do you identify application performance issues using monitoring tools, and how do you design solutions to resolve and prevent them?
```bash
I identify performance issues by correlating metrics, logs, and traces using monitoring tools like Prometheus, Grafana, and centralized logging to pinpoint bottlenecks.
Once identified, I resolve them by tuning resources, optimizing application or database queries, and fixing infrastructure constraints.
To prevent recurrence, I implement alerts, auto-scaling, performance baselines, and continuous monitoring with proactive capacity planning.
```
### 15. Explain s3 storage tiers and lifecycle rules?
```bash
Amazon S3 offers multiple storage tiers such as Standard, Intelligent-Tiering, Infrequent Access, and Glacier to optimize cost based on access frequency.
Lifecycle rules automatically move objects between these tiers or delete them after a defined time period.
This ensures cost optimization, durability, and efficient long-term data management.
```
