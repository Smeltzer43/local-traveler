# 🚨 URGENT: Create RLS Policy for Leads Table

## **The Problem**
Users are authenticating successfully, but leads are NOT being saved to the database because of RLS (Row Level Security) restrictions.

## **The Solution: Create RLS Policy**

### **Step 1: Go to Supabase Dashboard**
1. Open your browser and go to: https://supabase.com/dashboard
2. Sign in to your account
3. Click on your project: `jxytzukoqwmcrlldsbpo`

### **Step 2: Navigate to Authentication → Policies**
1. In the left sidebar, click **"Authentication"**
2. Click **"Policies"**
3. Find the **`public.leads`** table in the list

### **Step 3: Create Insert Policy**
1. Click **"New Policy"** next to the `leads` table
2. Choose **"For full customization"**
3. Fill in the form:
   - **Policy Name**: `Allow anonymous users to insert leads`
   - **Allowed Operation**: Select **"INSERT"**
   - **Target Roles**: Type `anon` (for anonymous users)
   - **Policy Definition**: Type `true`
4. Click **"Review"**
5. Click **"Save Policy"**

### **Step 4: Test the Fix**
1. Go to your live site: https://thelocaltravelers.com
2. Submit the popup form
3. Check your email and click the magic link
4. Go back to Supabase → **Table Editor** → **leads**
5. You should see the new lead data!

## **Alternative: Quick Fix (Temporary)**
If you want to test immediately without creating policies:

1. Go to **Table Editor** → **leads** table
2. Click the **RLS toggle** to **disable** it temporarily
3. Test your form
4. **Re-enable RLS** after testing

## **What This Policy Does**
- ✅ **Allows anonymous users** to insert lead data
- ✅ **Keeps RLS enabled** for security
- ✅ **Fixes the broken lead capture**
- ✅ **Maintains database security**

---

**This is the missing piece! Once you create this policy, your lead capture will work perfectly.** 🎯
