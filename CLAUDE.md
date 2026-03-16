# CLAUDE.md — Claude Code Quick Reference

## Project Overview
Claude Coach Kit is an open-source marketing automation toolkit for coaches and solopreneurs.

## Quick Commands
```bash
npm run dev          # Start development server
npm run build        # Production build
npm run lint         # Run linter
npm run send-emails  # Process email queue
npm run sync-sheets  # Sync Google Sheets
```

## Key Files
- `src/pages/` — Dashboard pages (20+ pages)
- `src/components/` — Reusable UI components
- `supabase/functions/` — Edge functions (webhooks, email, tracking)
- `scripts/` — Automation scripts

## Architecture
- Frontend: React 18 + Vite + TailwindCSS
- Backend: Supabase (PostgreSQL + Edge Functions)
- Email: Resend API or SMTP
- Payments: Razorpay webhooks

## Code Patterns
- Functional React components with hooks
- TailwindCSS utility classes (no CSS files)
- Supabase client for all DB operations
- Edge Functions for serverless webhooks
