# Getting Started with Coach Automation Kit

## Prerequisites
- Node.js 18+
- Supabase account (free tier)
- Email provider (Resend API or SMTP)

## Step 1: Clone & Install
```bash
git clone https://github.com/krishna-build/coach-automation-kit.git
cd coach-automation-kit
npm install
```

## Step 2: Supabase Setup
1. Create a project at supabase.com
2. Run the migrations: `npx supabase db push`
3. Copy your project URL and anon key

## Step 3: Environment Variables
```bash
cp .env.example .env
# Fill in your Supabase URL, keys, and email config
```

## Step 4: Start
```bash
npm run dev
```
Visit http://localhost:5173 🎉

## Step 5: Connect Your Payment Gateway
Add Razorpay webhook URL in your Razorpay dashboard pointing to your Supabase edge function.

## Step 6: Add UTM Tracking
Paste the tracking script from `scripts/utm-tracking.js` into your landing page header.
