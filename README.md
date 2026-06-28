**Project Overview**
VerdictOS is an agentic risk review solution that acts like an AI courtroom for enterprise decision. It receives incident from ServiceNow, extracts information from attachment, checks historical precedent from UiPath Data Fabric, runs multiple specialist agents, consolidates the debate into a final recommendation, routes high-risk cases for Upper management review, low-risk for human review (Approve or Reject) and records the final decision for audit and future precedent use.

**Wow factor:** Instead of one static rule engine, VerdictOS uses a multi-agent debate model where Finance, Cyber, Legal, Human Intent, Reputation and Precedent agents independently evaluate the case before a Debate Agent produces a controlled final recommendation.
Agent Type Indication
Agent Type	Project Fit
Hybrid	VerdictOS uses low-code agents built with UiPath Agent Builder / Maestro, supported by UiPath RPA workflows, Data Fabric lookups, ServiceNow integration, Slack notification and a lightweight coded dashboard/webhook service.

**UiPath Components Used**
•	UiPath Automation Cloud
•	UiPath Studio Web
•	UiPath Agent Builder / Maestro
•	UiPath Orchestrator
•	UiPath Data Fabric / Data Service entity for precedent history and final decision storage
•	UiPath Action Center / Human-in-the-loop task review
•	UiPath Integration Service / API-based application connections where applicable
•	UiPath RPA Workflow for Data Fabric lookup and final record storage

**Supporting Applications and Services**
•	ServiceNow for invoice validation incident intake and incident update
•	Slack for stakeholder/user notification
•	Local VerdictOS dashboard for demo visualization
•	Node.js local server for demo trigger/webhook service
•	ngrok for exposing local webhook/dashboard during demo, if required

**Prerequisites**
•	UiPath Automation Cloud account with access to the hackathon tenant/folder.
•	UiPath Studio Web access for Agentic Process and RPA Workflow editing.
•	UiPath Orchestrator access with robot/serverless execution configured for debugging or publishing.
•	Data Fabric unit allocated and the required Data Fabric entity created in the target tenant/folder.
•	ServiceNow test instance or mocked/demo incident source with invoice attachment.
•	Slack workspace/app/webhook or configured notification connector.
•	Node.js installed locally for the demo dashboard/webhook service.
•	ngrok installed and configured, if local webhook/dashboard needs to be exposed publicly during demo.
•	For Node.js and ngrok initialization refer to document - VerdictOS_DashboardIntegrationSteps


**Setup & Installation Instructions**
1.	Clone or download the repository: Download the VerdictOS repository and extract/open the project folder on the local machine.
2.	Start the local dashboard/webhook service: Open CMD inside the project folder and run the Node.js server command.
3.	Expose local service if required: Start ngrok for the local server port when ServiceNow/UiPath must reach the local webhook from the internet.
4.	Configure UiPath tenant resources: Ensure Orchestrator folder, robot/serverless runtime, assets/connections and Data Fabric units are available.
5.	Create/verify Data Fabric entity: Create or verify the Data Fabric entity used for case decision history and precedent lookup.
6.	Import/open UiPath solution: Open the VerdictOS solution in UiPath Studio Web.
7.	Configure ServiceNow incident trigger: Map Incident Number, Incident ID, attachment details and requester/business context from ServiceNow.
8.	Configure Data Fabric lookup workflow: Pass VendorName into the Data Fabric lookup workflow and return out_VendorHistory / VendorHistoryContext.
9.	Map Precedent Agent input: Pass VendorHistoryContext into the Precedent Agent so it can compare current vendor case with historical records.
10.	Configure final Data Fabric save workflow: Pass final decision, finance recommendation, risk score and incident details to the final Data Fabric save step.
11.	Run/debug the process: Run the Agentic Process from Studio Web or Orchestrator and validate dashboard, ServiceNow update, Slack notification and Data Fabric record creation.

**Agent Type Indication**
VerdictOS is a Low-Code Agent solution built using UiPath Agent Builder. It does not use custom-coded agents. The intelligence layer is created through low-code specialist agents, while UiPath workflows are used for orchestration, ServiceNow handling, Data Fabric lookup/storage, dashboard updates, Action Center tasks, and Slack notifications.

**Notes for Judges / Reviewers**
•	For sending data to Dashboard you need to refer document - VerdictOS_DashboardIntegrationSteps
•	You have to open dashboard manually from dashboard folder.
