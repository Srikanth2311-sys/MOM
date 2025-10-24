Azure DevOps Overview**  
---

**Cloud Computing**  
- Enables scaling, renting hardware, storage, and computing resources.  
- **CapEx**: Capital expenditure (upfront investment).  
- **OpEx**: Operational expenditure (recurring costs).

---

**Cloud Service Models**  
- **IaaS (Infrastructure as a Service)**:  
  Example: Amazon EC2  
  Full control over infrastructure. Suitable for lift-and-shift migrations like changing databases.  
  You manage: physical host, network, data center.

- **PaaS (Platform as a Service)**:  
  Example: AWS Elastic Beanstalk  
  Pay-per-use model. Avoid infrastructure administration.  
  You manage: OS, host, network, data center.

- **SaaS (Software as a Service)**:  
  Example: Amazon WorkMail  
  Used by end users like Office 365.  
  You manage: application, network, control, OS, host, data center.

---

**Environments**  
- **QA**: Quality Assurance  
- **SIT**: System Integration Testing  
- **PTE**: Performance Testing Environment

---

**Types of Testing**  
- **Sanity Testing**: Quick check after bug fix to ensure main functions work.  
- **Smoke Testing**: Basic test to verify app starts and major features are functional.  
- **Unit Testing**: Tests one small part of the code.  
- **Integration Testing**: Ensures different parts of the system work together.  
- **System Testing**: Tests the entire application as a complete system.  
- **Regression Testing**: Verifies old features still work after new changes.  
- **Performance Testing**: Checks speed and stability under load.  
- **Load Testing**: Tests behavior when many users access the app.  
- **Stress Testing**: Pushes the app beyond limits to see when it breaks.  
- **User Acceptance Testing (UAT)**: Final test by real users to confirm the app meets their needs.  
- **Security Testing**: Checks for vulnerabilities and protects against threats.

**Quick Reminders**  
- Sanity = Small fix, quick check  
- Smoke = Basic startup test  
- Regression = Old features still okay?  
- UAT = Real users approve it

---

**Development Models**  
- **Waterfall**  
- **Agile**

---

**DevOps Lifecycle Tools**  
- **Plan**: Jira, Azure Boards  
- **Code**: GitHub Repositories  
- **Build**: Gradle, Maven, Nexus Artifacts  
- **Test**: Azure Test Plans  
- **Release**: Jenkins, Azure Pipelines, GitLab  
- **Deploy**: AWS, Azure, GCP, Terraform  
- **Operate**: Chef, Puppet, Ansible, Kubernetes  
- **Monitor**: Prometheus, Grafana, Splunk

---

**DevOps Lifecycle Mapping**  
- **CI (Continuous Integration)**: Code → Build → Test  
- **CD (Continuous Delivery/Deployment)**: Release → Deploy  
- **CM (Configuration Management)**: Operate → Monitor

---
Azure Devops => org (git/tfvc,basic/agile,cmmi,scrum[work item]) => create
Summary, Dashboard, wiki,Board[jira],backlogs,repos[git],pipeline[build,release],Test plan,Artifacts[store the pkge to use  release pipeline env]
Azure devops service /Server.
it is used to track and work item like advacnc TODO list
work item -> epic, feature, US, task, bug => assign
Process => Basic (epic[app dev],issues[home], task[build nav]),Agile,CMMI, SCRUM.
Board [epic, issue] => kanban board
