# Setup Guide - Build #5: Review Generation Machine

## Prerequisites
- GoHighLevel account (Pro or higher)
- n8n instance (cloud or self-hosted)
- Google Business Profile with review link
- Twilio or GHL phone number for SMS

## Step 1: Environment Configuration
Copy .env.example to .env and fill in:
- GHL_API_KEY: Your GHL location API key
- GHL_LOCATION_ID: Your GHL location ID
- GOOGLE_REVIEW_LINK: Your Google Business review URL
- SLACK_WEBHOOK_URL: (Optional) Attorney notification webhook

## Step 2: n8n Workflow Setup
1. Import workflow-settled-won-trigger.json into n8n
2. Import workflow-review-followup.json into n8n
3. Configure GHL API credentials in n8n
4. Activate both workflows
5. Copy the webhook URL from workflow-settled-won-trigger.json

## Step 3: GHL Configuration
1. Create "Settled/Won" pipeline stage (see ghl/pipeline-stage-setup.md)
2. Create GHL custom fields for review tracking
3. Set up GHL automation webhook (see ghl/webhook-setup.md)
4. Add Google review link as GHL custom value

## Step 4: Test the System
1. Create a test contact in GHL
2. Move them to "Settled/Won" stage
3. Verify n8n receives the webhook
4. Confirm congratulations SMS is sent (10AM-6PM window)
5. After 48 hours, verify follow-up SMS fires if no review

## Step 5: Go Live
1. Set SEND_REAL_SMS=true in .env
2. Monitor first 5 real settlements
3. Check GHL dashboard for review conversion tracking

## Expected Results
- Review volume increase: 300-500%
- Average time to first review request: < 60 seconds after stage change
- Follow-up SMS sent at T+48 hours if no review detected
