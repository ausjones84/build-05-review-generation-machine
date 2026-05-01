# GHL Webhook Setup - Build #5 Review Generation Machine

## Overview
Configure GHL to send webhook data to n8n when a contact reaches "Settled/Won" stage.

## Step 1: Create n8n Webhook
1. In n8n, open workflow-settled-won-trigger.json
2. Copy the webhook URL (e.g., https://your-n8n.com/webhook/ghl-settled-won)

## Step 2: Configure GHL Automation Workflow
1. Go to GHL > Automation > Workflows > Create Workflow
2. Trigger: Opportunity Stage Changed
3. Filter: Stage = "Settled/Won"
4. Action: Webhook (POST)
5. URL: [paste your n8n webhook URL]
6. Include: contact_id, pipeline_stage_name, firstName, phone, email

## Step 3: Test
1. Move a test contact to Settled/Won stage
2. Check n8n execution log for received data
3. Verify SMS + email sent to test contact

## Payload Format
{
  "contact_id": "abc123",
  "pipeline_stage_name": "Settled/Won",
  "firstName": "John",
  "phone": "+15551234567",
  "email": "john@example.com"
}
