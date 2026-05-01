# SMS & Email Templates - Build #5 Review Generation Machine

## Initial Review Request (Triggered at Settled/Won)

### Primary SMS Template
Hi {{contact.firstName}}! Congratulations on settling your case! It has been an honor working with you. We have one small ask - would you mind leaving us a Google review? It takes 60 seconds and helps other injury victims find us: {{custom_values.google_review_link}} Thank you! - The Legal Team

### Email Template
Subject: Congratulations {{contact.firstName}}! Your Case is Settled

Body:
Hi {{contact.firstName}},

Congratulations on the successful settlement of your case! It has been our privilege to represent you.

Would you share your experience in a Google review? Your feedback helps other injury victims find trusted legal representation:

{{custom_values.google_review_link}}

It only takes 60 seconds and means the world to us.

With gratitude,
The Legal Team

## 48-Hour Follow-Up SMS

Hi {{contact.firstName}}, just a gentle reminder! We would love to hear about your experience with our firm. Your Google review helps other injury victims find trusted help: {{custom_values.google_review_link}} Thank you so much! - The Legal Team

## GHL Merge Fields Reference
- {{contact.firstName}} - Client first name
- {{custom_values.google_review_link}} - Google review URL (set in GHL Custom Values)
- {{contact.phone}} - Client phone number
- {{contact.email}} - Client email address
