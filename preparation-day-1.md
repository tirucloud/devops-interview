1. can you introduce yoursself?
2. on which project are you working currently?
3. on which tech olgy aare you working?
4. monolithic vs microservice arch?
5. what are the cahllenges you faced in the current project?
6. branching strategy?
7. prod deplyment happens through main/dev?
8. main vs master?
9. types of os disro's worked on in linux?
10. wget vs curl?
11. awk in linux?
12. free spcae in linux?
13. group in linux?
14. qulaity profile in sonar?
15. if code quality gate is falied then what willhappen?
16. what is master aand slave in jenkins?
17. if jenkins master is down, can job will run on slaves?
18. write jenkins pipeline?
19. if we mentioned same name for two stages in pipeline will it create a problem?
20. how to execute some of the stages in pipeline irrespective of subsequent stages passed or failed?
21. what are the plugins you installed in jenkins?
22. i want to trigger another job after succefully executing current job, how do you implement it?
23. how to trigger cd job after completion of ci job, how to implement it?
24. write ansible playbook?
25. why we nned passwordless auth in ansible?
26. run and cmd
27. copy and add
28. cmd and entrypoint
29. what is pod?
30. write pod maanifest file?
31. what is statefullset in k8s?
32. if lost my private key, can I aable to login to ec2 server?
33. l4 vs l7 load balancer?
34. nat gate way?
35. vpc peering vs transit gatteway?
36. sg vs nacl?


DevOps Interview Questions & Answers (3 Years Experience)
1. Can you introduce yourself?

Answer:
I’m a DevOps Engineer with around 3 years of experience in CI/CD automation, cloud infrastructure, and containerized deployments. I’ve worked extensively with Jenkins, Git, Docker, Kubernetes, AWS, and monitoring tools. My role mainly involves automating build and deployment pipelines, managing cloud resources, and ensuring application reliability and scalability.

2. Which project are you currently working on?

Answer:
I’m currently working on a microservices-based application where we automate CI/CD pipelines, deploy workloads on Kubernetes, manage AWS infrastructure, and monitor application performance using Prometheus and Grafana.

3. Which technologies are you working with?

Answer:
Git, GitHub/GitLab, Jenkins, Docker, Kubernetes, Ansible, Terraform, AWS (EC2, S3, IAM, ALB, VPC), SonarQube, Prometheus, Grafana, Linux, and Shell scripting.

4. Monolithic vs Microservices architecture?

Answer:
Monolithic architecture has all components in a single codebase and deployment unit, which is simpler but hard to scale.
Microservices architecture breaks the application into independent services, allowing better scalability, fault isolation, and faster deployments.

5. What challenges did you face in your current project?

Answer:
Handling CI/CD pipeline failures, managing Kubernetes pod restarts, environment-specific configuration issues, ensuring zero-downtime deployments, and improving build performance.

6. What branching strategy do you use?

Answer:
We follow GitFlow, using feature branches for development, develop for integration, and main for production-ready code.

7. Does production deployment happen through main or dev?

Answer:
Production deployments always happen through the main branch. The dev branch is used for integration and testing.

8. Main vs Master branch?

Answer:
Both serve the same purpose, but main is the modern default naming convention, replacing master.

9. Which Linux OS distributions have you worked on?

Answer:
Ubuntu, Amazon Linux, Red Hat Enterprise Linux (RHEL), and CentOS.

10. wget vs curl?

Answer:
wget is mainly used for downloading files.
curl is more flexible and supports APIs, headers, authentication, and multiple protocols.

11. What is awk in Linux?

Answer:
awk is a text-processing tool used for pattern scanning and reporting, commonly used for parsing logs and structured text.

12. How do you check free disk space in Linux?

Answer:
Using df -h for filesystem usage and du -sh for directory-level usage.

13. What is a group in Linux?

Answer:
A group is a collection of users that helps manage file and resource permissions efficiently.

14. What is a Quality Profile in SonarQube?

Answer:
A Quality Profile is a set of coding rules applied during code analysis to detect bugs, vulnerabilities, and code smells.

15. What happens if the SonarQube Quality Gate fails?

Answer:
The pipeline fails, and the code is not promoted to the next stage, preventing poor-quality code from reaching production.

16. What is master and slave in Jenkins?

Answer:
The master manages jobs and scheduling, while slaves (agents) execute the jobs.

17. If Jenkins master is down, will jobs run on slaves?

Answer:
No. The master is required to schedule and manage jobs, so builds will not run.

18. Write a simple Jenkins pipeline.
pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building application'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying application'
      }
    }
  }
}

19. If two pipeline stages have the same name, will it cause an issue?

Answer:
Yes. Jenkins requires unique stage names for proper visualization and execution tracking.

20. How do you run stages irrespective of success or failure?

Answer:
Using the post block or catchError in Jenkins pipeline.

21. Which Jenkins plugins have you used?

Answer:
Git, Pipeline, Docker, Kubernetes, SonarQube Scanner, Email Extension, Blue Ocean, and Credentials Binding.

22. How do you trigger another job after successful execution?

Answer:
Using the build job: option in Jenkins pipeline or post-build actions.

23. How do you trigger a CD job after a CI job?

Answer:
By configuring the CI pipeline to trigger the CD pipeline using downstream jobs or webhooks.

24. Write a simple Ansible playbook.
- hosts: web
  become: yes
  tasks:
    - name: Install nginx
      apt:
        name: nginx
        state: present

25. Why do we need passwordless authentication in Ansible?

Answer:
To automate tasks securely without manual password entry using SSH key-based authentication.

26. RUN vs CMD in Docker?

Answer:
RUN executes commands at image build time.
CMD runs when the container starts.

27. COPY vs ADD in Docker?

Answer:
COPY copies local files only.
ADD supports URLs and auto-extracts archives.

28. CMD vs ENTRYPOINT?

Answer:
ENTRYPOINT defines the main container process.
CMD provides default arguments that can be overridden.

29. What is a Pod?

Answer:
A Pod is the smallest deployable unit in Kubernetes that can contain one or more containers.

30. Write a Pod manifest file.
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
spec:
  containers:
    - name: nginx
      image: nginx

31. What is a StatefulSet in Kubernetes?

Answer:
StatefulSet is used for stateful applications requiring stable network identity and persistent storage.

32. If you lose your EC2 private key, can you log in?

Answer:
No. You must create a new key by detaching the root volume or using AWS Systems Manager if enabled.

33. Layer 4 vs Layer 7 load balancer?

Answer:
Layer 4 works at TCP/UDP level.
Layer 7 works at HTTP/HTTPS level with routing based on URLs and headers.

34. What is a NAT Gateway?

Answer:
A NAT Gateway allows private subnet instances to access the internet without exposing them publicly.

35. VPC Peering vs Transit Gateway?

Answer:
VPC Peering is point-to-point and not transitive.
Transit Gateway provides scalable, hub-and-spoke connectivity.

36. Security Group vs NACL?

Answer:
Security Groups are stateful and instance-level.
NACLs are stateless and subnet-level.
