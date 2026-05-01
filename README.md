# Build #5: Review Generation Machine

**Stack:** GHL + n8n + Google Business API  **Pricing:** $800 setup + $297/month  **Problem Solved:** Settled clients never leave Google reviews

## Overview

Build #5 is a fully automated review generation system that triggers when a PI case is marked as "Settled/Won" in GHL. It sends a congratulations SMS with a review request link at the optimal time, follows up 48 hours later if no review is left, and tracks review conversion directly in the GHL dashboard.

## How It Works

1. **GHL Pipeline Trigger** - Workflow fires when opportunity stage moves to "Settled/Won"
2. 2. **Congratulations SMS + Review Link** - Client receives personalized congratulations text with direct Google review link sent at optimal time (10 AM - 6 PM window)
   3. 3. **48-Hour Follow-Up** - If no review detected within 48 hours, sends a polite reminder SMS
      4. 4. **Review Tracking** - GHL dashboard custom field updated when review is confirmed via Google Business API
         5. 5. **Attorney Notification** - Firm notified when client leaves a review (positive reinforcement loop)
           
            6. ## File Structure
           
            7. ```
               build-05-review-generation-machine/
               README.md
               n8n/workflow-settled-won-trigger.json
               n8n/workflow-review-followup.json
               ghl/pipeline-settled-won-setup.md
               ghl/sms-review-templates.md
               ghl/webhook-setup.md
               docs/setup-guide.md
               docs/pricing.md
               .env.example
               ```

               ## Pricing

               | Package | Price |
               |---|---|
               | Setup Fee (one-time) | $800 |
               | Monthly Retainer | $297/month |

               ## Key Features

               - Trigger fires within 60 seconds of "Settled/Won" pipeline stage update
               - - Smart timing: SMS sent only between 10 AM - 6 PM (client's local time)
                 - - 48-hour automated follow-up if no review submitted
                   - - Google Business API polling to detect review completion
                     - - GHL dashboard tracks review conversion rate
                       - - Attorney/firm notification on review receipt
                         - - Increases Google review volume by 300-500%
