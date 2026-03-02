Email Triage & Auto-Responder

Team Members
Rimsha Tahir  – Email Ingestion + Classification & Routing – GitHub: rimshatahir
Sabina Ruzieva – Auto Response Drafting – GitHub: sabinova
Zainab Chaudhry – Integration, Testing & Dashboard – GitHub: zainabc22
Problem Statement
In many workplaces, email inboxes quickly become overwhelming. Important or urgent messages can easily get buried under routine questions, informational emails, and spam. Sorting and responding to emails manually takes time and can lead to delays or missed requests. Our project builds an AI-powered email triage and auto-responder system that automatically classifies emails by category and urgency, drafts responses for common types of emails, and routes important messages to the correct queue for human review.
Target Users
This system is designed for small teams, student organizations, help-desk environments, or businesses that receive a high volume of emails and need help organizing and prioritizing them. It is especially useful in situations where quick responses and structured workflows are important.
Architecture
![Architecture Diagram](docs/architecture.png)




Component Breakdown
Component 1: Email Ingestion + Classification & Routing
Owner: Rimsha Tahir
This component builds an n8n workflow that captures incoming emails using either a webhook simulation or a test inbox. It extracts the sender, subject, body, and timestamp, and stores the information in Airtable. After storing the email, the workflow sends the email text to the Hugging Face API to classify it into a category (question, complaint, request, informational, spam) and assign an urgency level (low, medium, high). The system then updates the Airtable record and routes the email into the correct queue view.
Tools Used:
n8n, Airtable, Hugging Face API
Input:
Raw email data (sender, subject, body, timestamp)
Output:
Updated Airtable record with category, urgency, confidence score, and status set to CLASSIFIED
Standalone Demo:
Show at least 10 sample emails being automatically classified and placed into the correct Airtable views.
Component 2: Auto Response Drafting
Owner: Sabina Ruzieva
This component creates a Flowise LLM chain that generates draft responses for common email types, such as answering questions, acknowledging complaints, or responding to requests. The draft is saved in Airtable in a review queue so that a human can approve or edit it before sending. This keeps the system automated but still controlled.
Tools Used:
Flowise, Groq API or Hugging Face text generation API, n8n, Airtable
Input:
Classified email (category, urgency, subject, body)
Output:
Draft response stored in Airtable with status set to NEEDS_REVIEW
Standalone Demo:
Generate draft replies for at least 5 emails and show them appearing in the review queue.
Component 3: Integration, Testing & Dashboard
Owner: Zainab Chaudhry
This component designs the Airtable base, including the Emails table, Response Drafts table, and any linked records needed. It also creates at least 30 test emails across all categories and urgency levels. In addition, this component builds dashboard views in Airtable that show category breakdown, urgency distribution, and a Kanban-style view for emails that need human review. This role ensures that all components connect correctly and prepares the final demo and documentation.
Tools Used:
Airtable, GitHub, draw.io
Input:
Data generated from Components 1 and 2
Output:
A fully working, integrated system with dashboard views and clear documentation
Standalone Demo:
Show one email moving through the entire system: NEW → CLASSIFIED → DRAFT GENERATED → REVIEWED → APPROVED.
Data Sources
Primary Data:
We will create a simulated set of test emails that reflect realistic workplace communication.
Sample Data:
At least 30 emails across different categories (questions, complaints, requests, informational messages, and spam) with different urgency levels.
Data Format:
Webhook JSON payloads or structured CSV data processed by n8n and stored in Airtable.
AI Capabilities
Text Classification – Categorizes incoming emails
Urgency Detection – Assigns urgency level (low, medium, high)
Confidence Scoring – Shows how confident the model is in its classification
Response Generation – Creates draft replies for selected email types
APIs/Models Used:
Hugging Face Inference API and Groq or Hugging Face text generation models through Flowise.
Success Criteria
The system correctly classifies at least 80% (24 out of 30) test emails.
Urgency levels are correctly assigned for at least 80% of emails.
Draft responses are generated for at least three categories of emails.
The dashboard clearly shows category distribution and urgency breakdown.
The full workflow runs smoothly from ingestion to draft generation without manual data transfer.
The GitHub repository includes clear documentation and setup instructions.


Timeline
Week 3 – Proposal, architecture diagram, and GitHub setup
Weeks 4–6 – Build ingestion and classification workflows
Weeks 7–9 – Implement response drafting and improve prompts
Weeks 10–12 – Integration testing and dashboard improvements
Weeks 13–14 – Final documentation and demo preparation
Week 15 – Final presentation

