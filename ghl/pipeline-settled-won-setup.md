# GHL Pipeline Setup: Settled/Won Stage

## Overview
Build #5 Review Generation Machine - GHL pipeline configuration.

## Required Pipeline Stage
Name: **Settled/Won**

## Setup Steps
1. Navigate: CRM > Pipelines > Edit PI Law Firm pipeline
2. 2. Add stage named exactly: `Settled/Won`
   3. 3. Configure webhook to fire to n8n on stage entry
     
      4. ## GHL Custom Fields to Create
      5. - `review_requested_at` (Date/Time) - timestamp when review was requested
         - - `review_left` (Checkbox) - true when Google review confirmed
           - - `review_followup_sent` (Checkbox) - true when 48hr follow-up sent
            
             - ## Webhook Configuration
             - - Event: Opportunity Stage Changed
               - - Stage Filter: Settled/Won
                 - - Payload: contact_id, pipeline_stage_name, contact details
                   - - Destination: n8n Webhook URL (from workflow-settled-won-trigger.json)
                    
                     - ## GHL Tags Used by This Build
                     - - `review-requested` - applied after initial SMS sent
                       - - `review-followup-sent` - applied after 48hr follow-up SMS
                         - - `review-left` - applied when Google review confirmed
