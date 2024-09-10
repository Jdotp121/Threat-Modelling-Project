# Project Summary

Application Summary: "TaskHub" - A Project Management Web Application
TaskHub is a cloud-based project management application designed to help teams organize tasks, track project progress, and collaborate in real-time. The application is built using a modern microservices architecture, leveraging a RESTful API and a web-based frontend, accessible on both desktop and mobile devices.

Key Features:

User Authentication and Authorization:
Users can sign up using an email/password combination or OAuth via Google and GitHub.
Role-based access control (RBAC) to assign different permissions to users (Admin, Manager, Team Member).
Task Management:
Users can create, assign, and track tasks with due dates, priorities, and labels.
Task status is updated in real-time, and tasks can be assigned to multiple users.
Project Collaboration:
Teams can collaborate on shared projects, with a dedicated chat and document-sharing functionality.
Activity logs track changes to tasks and project data.
API Integrations:
The application integrates with third-party services like Slack, Google Drive, and GitHub to provide notifications and file storage.
Data Storage:
All task and project data is stored in a cloud-based NoSQL database (e.g., MongoDB).
User data, such as passwords and OAuth tokens, are stored securely in a relational database (e.g., PostgreSQL).
Notifications and Alerts:
Users can configure push notifications for task updates, project milestones, and deadlines.
Email notifications are sent for important updates and reminders.
Multi-Tenant Architecture:
The application supports multiple organizations, with isolated data for each team.
Admins within each organization can manage their users, projects, and tasks independently.
Deployment and Infrastructure:
Hosted on AWS with Kubernetes for container orchestration.
Load balancers and autoscaling groups ensure high availability and performance.
Traffic to and from the application is secured using HTTPS (TLS).

# Threat Modelling Workshop Summary

## Introduction
A 3 Hour threat modelling workshop took place to detail the runbook scenario of multiple AI attacks against the web-facing application TaskHub.

## Attendess
Care Connect Eng team, Product Managers, DevEx Engineers and the DevSecOps Team.

## Scope
4 Scenarios were run covering: (1) AI Generated External phishing email utilising admin credentials, (2) Authentication Risks: Password brute-force attacks and (3) Data Breach: Unauthorized access to sensitive data (e.g., task information, user credentials) via SQL Injection attack 

## Methodology
All scenarios were run against the cyber attack killchain, utilising the Mitre Att&ack framework and STRIDE for control gap assessments. Culminating in identified risks. 

## Conclusion
A total of 4 high risks and 1 medium risks were found during the threat modelling workshop.

## Controls Required

- Regular security audits using ASVS specifically targeting the Taskhub application to detect vulnerabilities and weaknesses in its security measures.
- Patch management to ensure the Taskhub application and its underlying technologies are up-to-date and protected against known vulnerabilities.
- Mitigation against DDoS: Rate limiting, load balancing, DDoS protection.
- Comprehensive employee training on phishing awareness to educate users of the Taskhub application about the risks of phishing attacks and how to identify and report suspicious emails.
- Implementation of a Web Application Firewall (WAF) tailored to the Taskhub application's traffic to monitor and filter incoming requests for malicious activity, to detect and block SQL injection attempts at the network level. This adds an extra layer of defense against known SQL injection patterns.
- Deployment of Multi-factor Authentication (MFA) to enhance authentication security and prevent unauthorized access to the Taskhub application.
- Continuous network traffic monitoring to detect and respond to suspicious activity within the Taskhub application's infrastructure.

# Threat Modelling Process Summary

```mermaid
mindmap
  root((Attack Begins))
    STRIDE/MITRE ATT&CK/Kill Chain
      Conduct Inherent Risk Assesment
      ::icon(fa fa-book)
      Create Critical Asset List
        Schedule and Scope Threat Modelling Workshop
    Controls Required
      Risks<br/>Mitigations
      Risk Summary
        Redmeiation workflow
            Slack
            JIRA 
    Attack Scenarios
      Attack 1
      Attack 2
      Attack 3
      Attack 4

