# Architecture

## System Overview

Coach Automation Kit follows a serverless architecture with Supabase as the backbone.

### Data Flow
1. **Visitor lands on landing page** → UTM tracking script fires → data saved to `utm_visitors` table
2. **Lead submits form** → Google Sheet webhook → synced to `automation_contacts`  
3. **Payment completed** → Razorpay webhook → Edge Function matches visitor → updates contact
4. **Auto-enrollment** → Cron job checks new leads → enrolls in email sequence
5. **Email sending** → Cron job processes sequence queue → sends via SMTP/Resend

### Database Tables
- `automation_contacts` — All leads and customers
- `utm_visitors` — Ad click tracking data
- `email_sequences` — Sequence definitions
- `sequence_enrollments` — Active enrollments
- `sequence_steps` — Individual email steps
- `email_logs` — Delivery tracking

### Edge Functions
- `track-visitor` — Captures UTM data + geolocation
- `razorpay-webhook` — Payment processing + visitor matching
- `email-engine` — Email sending with SMTP/Resend
- `sync-master-sheet` — Google Sheet bidirectional sync
