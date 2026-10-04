# AI-Powered Website Lead Automation

An n8n automation that processes website contact form submissions, uses AI to classify inquiries, and automatically creates potential client leads in Zoho CRM.

## Overview

This project connects a WordPress Contact Form 7 form with n8n and Zoho CRM.

When a visitor submits the contact form, the workflow receives the submission through an n8n webhook, validates the email address, uses AI to classify the inquiry, and routes the submission based on its category.

Potential client inquiries are prepared as lead data and automatically created in Zoho CRM.

## Problem

Website inquiries can require manual processing:

* Reading every contact form submission
* Identifying whether the inquiry is from a potential client, recruiter, or general visitor
* Copying lead information into a CRM
* Re-entering the same information manually

This automation reduces those repetitive steps.

## Solution

The workflow automates the initial lead-processing process:

1. Receive the website contact form submission.
2. Validate the submitted email address.
3. Use AI to classify the inquiry.
4. Route the inquiry based on its classification.
5. Prepare the lead information.
6. Create a lead in Zoho CRM for potential clients.

## Workflow

The automation follows this process:

```text
WordPress Contact Form 7
          │
          ▼
    n8n Webhook
          │
          ▼
    Validate Email
          │
          ▼
    AI Classification
          │
          ▼
     Route Inquiry
      ┌───┼───────────────┐
      │   │               │
      ▼   ▼               ▼
Potential Hiring     General / Spam
Client
  │
  ▼
Prepare Lead Data
  │
  ▼
Create Zoho Lead
  │
  ▼
Zoho CRM
```

### Workflow Components

| Component             | Purpose                                        |
| --------------------- | ---------------------------------------------- |
| **Contact Form 7**    | Collects website visitor inquiries             |
| **n8n Webhook**       | Receives the submitted form data               |
| **Validate Email**    | Checks whether an email address was provided   |
| **AI Classification** | Determines the type of inquiry                 |
| **Route Inquiry**     | Sends the submission to the appropriate branch |
| **Prepare Lead Data** | Formats the information for Zoho CRM           |
| **Zoho CRM**          | Creates a lead for potential clients           |

### AI Classification

The AI classifies incoming inquiries into four categories:

* `potential_client`
* `hiring`
* `general_inquiry`
* `spam`

Potential client inquiries are currently routed to the Zoho CRM lead creation process.
