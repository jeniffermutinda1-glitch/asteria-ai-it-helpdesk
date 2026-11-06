# Workflow Configuration and User Guide

## 1. Introduction

This guide explains how the two Asteria AI IT Helpdesk Assistant workflows operate and how employees and technicians interact with them.

## 2. Employee Incident Submission

### Employee responsibilities

1. Open the employee incident submission form.
2. Enter your name.
3. Enter your email address.
4. Select your department.
5. Describe the IT problem clearly.
6. Submit the form.

### Automated processing

After submission, the system:

1. Sends the incident description for AI analysis.
2. Determines an incident category, severity and priority.
3. Generates an incident summary and recommended actions.
4. Determines whether escalation is required.
5. Generates a Ticket ID.
6. Registers the incident in Google Sheets.
7. Sends an acknowledgement email.
8. Sends an escalation email when required.

Employees should retain their Ticket ID for future reference.

## 3. Technician Update Portal

### Technician responsibilities

1. Open the technician update portal.
2. Enter the existing Ticket ID.
3. Select the technician's name.
4. Select the updated incident status.
5. Enter resolution notes or progress information.
6. Submit the update.

### Supported statuses

- Assigned
- In Progress
- Escalated
- Resolved
- Closed

### Automated processing

The workflow retrieves the existing incident using its Ticket ID and updates the matching record.

It also refreshes the Last Updated timestamp.

When the incident becomes Resolved, the workflow records the Resolution Date. If the incident subsequently changes to Closed, the existing Resolution Date is preserved.

## 4. Incident Register

Authorized support personnel can use the shared Google Sheets incident register to review:

- Employee and department information.
- Incident category, severity and priority.
- AI-generated summary and recommended actions.
- Escalation requirements.
- Assigned technician.
- Current status.
- Resolution notes and timestamps.

## 5. Operational Notes

- A valid Ticket ID is required for technician updates.
- Technicians must enter the Ticket ID manually in the current version.
- Invalid Ticket IDs do not update existing incident records.
- AI-generated recommendations should be reviewed by IT Support.
- Do not enter patient information, passwords or other confidential data into the demonstration forms.

## 6. Administration and Maintenance

The workflow administrator should periodically:

- Verify workflow execution history.
- Check email delivery.
- Review failed executions.
- Confirm Google Sheets connectivity.
- Review AI classification quality.
- Maintain secure credentials.
- Review access permissions.

## 7. Important Deployment Notice

This guide describes a portfolio demonstration. Before organizational deployment, the system requires security review, appropriate authentication, access control, data protection measures and operational monitoring.
