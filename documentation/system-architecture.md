System Architecture

 1. Overview

The Asteria AI IT Helpdesk Assistant consists of two independent n8n workflows connected through a shared Google Sheets incident register.

The system uses AI to analyze employee incidents and automation to manage ticket registration, notifications and technician updates.

 2. Architecture Components

 Component                 Responsibility 

 Employee Intake Form      Collects employee and incident information 
 n8n Workflow 1            Processes and registers incidents 
 Google Gemini             Analyzes and classifies incidents 
 Google Sheets             Stores incident records 
 Gmail                     Sends notifications and escalations 
 Technician Update Form    Collects technician updates 
 n8n Workflow 2           Retrieves and updates existing incidents 

 3. Workflow 1: Employee Incident Processing

Process flow:

Employee → Intake Form → Gemini AI Analysis → Ticket ID Generation → Google Sheets → Employee Email

A conditional branch sends an escalation email to IT Support when the AI analysis identifies that escalation is required.

Processing stages

1. Employee submits their name, email, department and issue description.
2. The Basic LLM Chain sends the incident information for AI analysis.
3. Gemini returns structured incident information.
4. n8n generates a unique ticket reference.
5. Google Sheets stores the incident.
6. Gmail sends the employee an acknowledgement.
7. A conditional workflow sends an escalation notification when required.

 4. Workflow 2: Technician Incident Updates

Process flow:

Technician Update Form → Ticket Lookup → Status Condition → Google Sheets Update

 Processing stages

1. Technician enters the Ticket ID.
2. The workflow searches the incident register.
3. An IF node checks whether the updated status is Resolved.
4. The Update Row node updates the existing incident.
5. Last Updated records the latest change.
6. Resolution Date is recorded when the incident becomes Resolved and retained when its status subsequently changes.

Both IF branches connect to the update operation. The date expression ensures that a previously recorded resolution date is preserved.

 5. Shared Data Store

Google Sheets is the central incident register used by both workflows.

The employee intake workflow creates incident records. The technician workflow retrieves and updates those records using the Ticket ID.

This approach keeps incident information in one shared location.

 6. AI Classification Outputs

The AI analysis produces:

- Incident Category
- Severity
- Priority
- Escalation Required
- Incident Summary
- Recommended Actions

AI-generated classifications are decision-support information and should be reviewed by an authorized IT professional.

 7. Design Considerations

- Ticket IDs provide a reference for retrieving incidents.
- Existing incident rows are updated rather than creating new rows during technician updates.
- Conditional escalation supports faster attention to serious incidents.
- Resolution timestamps support incident lifecycle tracking.
- Human oversight remains necessary for incident response decisions.

 8. Deployment Considerations

This implementation is a demonstration environment using personal Google services.

A production deployment would require appropriate organizational accounts, access controls, secure credential management, monitoring, backups and privacy controls.

No real patient or confidential organizational information should be used in this demonstration.
