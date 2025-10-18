# Supabase Setup Guide

## 1. Create Supabase Project

1. Go to [supabase.com](https://supabase.com)
2. Sign up for a free account
3. Create a new project
4. Choose a project name (e.g., "sales-funnel")
5. Select a region close to your users
6. Set a database password

## 2. Get Your Credentials

1. Go to **Settings** → **API** in your Supabase dashboard
2. Copy the following values:
   - **Project URL** → Replace `YOUR_SUPABASE_URL` in index.html
   - **Anon public key** → Replace `YOUR_SUPABASE_ANON_KEY` in index.html

## 3. Create Database Table

Run this SQL in your Supabase SQL Editor:

```sql
-- Create leads table
CREATE TABLE leads (
  id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
  first_name TEXT NOT NULL,
  last_name TEXT NOT NULL,
  email TEXT UNIQUE NOT NULL,
  source TEXT DEFAULT 'popup',
  status TEXT DEFAULT 'new',
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Add indexes for better performance
CREATE INDEX idx_leads_email ON leads(email);
CREATE INDEX idx_leads_created_at ON leads(created_at);
CREATE INDEX idx_leads_source ON leads(source);

-- Enable Row Level Security (optional)
ALTER TABLE leads ENABLE ROW LEVEL SECURITY;

-- Create policy to allow inserts (adjust as needed)
CREATE POLICY "Allow public inserts" ON leads
  FOR INSERT WITH CHECK (true);
```

## 4. Update Your HTML

Replace these values in your `index.html`:

```javascript
// Line 729-730 in index.html
const SUPABASE_URL = 'YOUR_SUPABASE_URL'; // Replace with your actual URL
const SUPABASE_ANON_KEY = 'YOUR_SUPABASE_ANON_KEY'; // Replace with your actual key
```

## 5. Test the Integration

1. Open your HTML file in a browser
2. Click any popup trigger button
3. Fill out the form with test data
4. Submit the form
5. Check your Supabase dashboard → Table Editor → leads table
6. You should see your test data!

## 6. Optional: Real-time Notifications

To see leads in real-time, you can add this to your Supabase dashboard:

```sql
-- Create a real-time subscription (optional)
-- This will show new leads as they come in
```

## Troubleshooting

- **CORS errors**: Make sure your domain is added to Supabase allowed origins
- **Permission errors**: Check your RLS policies
- **Connection errors**: Verify your URL and keys are correct

## Next Steps

- Set up email automation (ConvertKit, Mailchimp)
- Add custom redirects based on lead source
- Create analytics dashboard
- Set up lead scoring


