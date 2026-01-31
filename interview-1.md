## interview-1


1. How do you decide the number of target groups to configure for an Application Load Balancer?
2. How many target groups are typically configured behind an Application Load Balancer?
3. Can you explain the end-to-end flow of a user request, starting from accessing an application URL to how the request reaches and interacts with the database?
	```bash
	How is authentication handled in this flow?

	Where does caching fit in?

	How is database connection pooling managed?

	What happens if the database is temporarily unavailable?
	```
4. How would you implement user-specific access control for S3 objects in a production environment?
5. Are you using api gateway in architeccture or alb?
```bash
 I choose between API Gateway and Application Load Balancer based on the type of traffic and responsibilities in the architecture. In many cases, I use both together.
```
6. How do you perform Linux server patching in a production environment while minimizing downtime and risk?
7. In your experience, what has been the maximum application downtime, and how was it handled?
```bash

“In my experience, the maximum application downtime was around 20–25 minutes during a production incident.”

What happened:

“It was caused by a failed deployment combined with an unexpected dependency issue, which led to application pods becoming unhealthy.”

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

“Since implementing these changes, we’ve avoided similar outages and reduced deployment-related risk significantly.”
```
8. write jenkins pipeline?


9. why are you using multiple tools for monitoring (elk, prometheus and grafana)?
``bash
Using ELK, Prometheus, and Grafana together gives us full observability—metrics for detection, logs for diagnosis, and dashboards for visibility.Because no single tool covers logs, metrics, and visualization end-to-end. Each tool solves a different observability problem.
```	
11. what is crontab?
12. can you wrtite shell script and python script for automation?
