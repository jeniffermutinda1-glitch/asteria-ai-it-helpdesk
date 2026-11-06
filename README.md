 Asteria AI IT Helpdesk Assistant

An AI-powered IT incident management and helpdesk automation system built with **n8n, Google Gemini, Google Sheets and Gmail**.

 Project Overview

Asteria Health Systems is a fictional organization used to demonstrate how AI and workflow automation can improve IT service management.

The project automates employee incident reporting, AI-assisted incident classification, ticket registration, email notifications and technician updates. It consists of two n8n workflows that use a shared Google Sheets incident register.

 Business Problem

Traditional IT helpdesk processes can involve manual incident recording, inconsistent categorization, delayed escalation and limited visibility into incident progress.

This project demonstrates how workflow automation and AI can reduce repetitive administrative work and improve incident tracking.

 Key Features

- Employee incident submission through an online form.
- AI-assisted incident classification and summarization.
- Automatic ticket ID generation.
- Centralized incident registration using Google Sheets.
- Employee acknowledgement emails.
- Conditional IT Support escalation emails.
- Technician assignment and incident status updates.
- Resolution notes and date tracking.

 Technology Stack

| Technology | Purpose |
|---|---|
| n8n | Workflow automation |
| Google Gemini | AI incident analysis |
| Google Sheets | Incident register |
| Gmail | Email notifications |
| JavaScript expressions | Workflow logic and ticket ID generation |

 System Architecture

 Workflow 1: Employee Incident Intake

1. Employee submits an IT incident through an n8n form.
2. Google Gemini analyzes the incident.
3. AI generates incident category, severity, priority, summary, recommended actions and escalation decision.
4. n8n generates a unique Ticket ID.
5. Incident details are saved to Google Sheets.
6. An acknowledgement email is sent to the employee.
7. IT Support receives an escalation email when required.

 Workflow 2: Technician Update Portal

1. Technician submits a Ticket ID through a separate form.
2. The workflow searches the Google Sheets incident register.
3. Technician provides their name, updated status and resolution notes.
4. The workflow checks whether the incident is marked Resolved.
5. The existing incident row is updated.
6. Last Updated is refreshed.
7. Resolution Date is recorded when resolved and preserved when subsequently closed.

 Incident Register

The shared Google Sheets register contains:

- Ticket ID
- Employee Name
- Employee Email
- Department
- Issue Description
- Incident Category
- Severity
- Priority
- Incident Summary
- Recommended Actions
- Escalation Required
- Status
- Assigned Technician
- Resolution Notes
- Last Updated
- Resolution Date

 Testing and Validation

| Test | Result |
|---|---|
| Employee incident submission | Passed |
| AI incident classification | Passed |
| Automatic ticket generation | Passed |
| Google Sheets registration | Passed |
| Employee acknowledgement email | Passed |
| Conditional escalation email | Passed |
| Technician assignment and status updates | Passed |
| Resolution notes saved | Passed |
| Resolution date recorded and preserved | Passed |
| Existing ticket updated without duplicate row | Passed |
| Invalid Ticket ID did not modify an existing record | Passed; feedback needs improvement |

 Known Limitations

- Technicians manually enter Ticket IDs.
- Invalid ticket submissions do not yet display a dedicated user-friendly error.
- AI recommendations require human review.
- Google Sheets is a demonstration data store, not a dedicated enterprise ITSM database.
- The project has not undergone enterprise security or production-readiness testing.

 Future Improvements

- Dynamic incident selection in the technician portal.
- Better invalid-ticket feedback and error handling.
- Role-based access control and stronger authentication.
- Incident analytics and reporting dashboards.
- Service-level agreement (SLA) tracking.
- Monitoring and audit logging.
- Integration with a dedicated IT service management platform.

 Security and Data Handling

This is an educational portfolio demonstration.

Never publish API keys, passwords, OAuth tokens, real employee information, confidential organizational data or live production webhook URLs. Inspect and sanitize n8n workflow exports before publishing them.

 Project Status

Core MVP completed and tested.

This project demonstrates practical skills in AI integration, workflow orchestration, data handling, email automation and IT service management.

 Author

Developed as a practical portfolio project in Cloud and AI Automation.
