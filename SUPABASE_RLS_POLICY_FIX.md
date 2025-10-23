# URGENT: Supabase RLS Policy Fix for Leads Table

## 🚨 **Problem**
After enabling RLS on the `public.leads` table, users can no longer insert lead data because the anonymous user doesn't have permission.

## 🔧 **Solution: Create RLS Policy**

### **Step 1: Go to Supabase Dashboard**
1. Go to your Supabase project dashboard
2. Navigate to **Authentication** → **Policies**
3. Find the `public.leads` table

### **Step 2: Create Insert Policy**
1. Click **"New Policy"** for the `leads` table
2. Choose **"For full customization"**
3. **Policy Name**: `Allow anonymous users to insert leads`
4. **Allowed Operation**: `INSERT`
5. **Target Roles**: `anon` (anonymous users)
6. **Policy Definition**:
```sql
true
```

### **Step 3: Create Select Policy (Optional)**
If you want to allow reading leads (for admin purposes):
1. **Policy Name**: `Allow authenticated users to read leads`
2. **Allowed Operation**: `SELECT`
3. **Target Roles**: `authenticated`
4. **Policy Definition**:
```sql
true
```

### **Step 4: Test the Fix**
1. Go to your live site
2. Try the popup form
3. Check the `leads` table in Supabase
4. Verify the lead data is inserted

## 🎯 **What This Does**
- ✅ **Allows anonymous users** to insert lead data
- ✅ **Maintains security** by only allowing inserts
- ✅ **Fixes the broken lead capture**
- ✅ **Keeps RLS enabled** for security

## 📋 **Alternative: Disable RLS (Not Recommended)**
If you want to disable RLS temporarily:
1. Go to **Table Editor** → **leads** table
2. Click the **RLS toggle** to disable it
3. **Warning**: This removes security protection

## 🔍 **Verify the Fix**
After creating the policy, test:
1. Submit the popup form
2. Check Supabase → **Table Editor** → **leads**
3. Verify new lead appears in the table

---

**This policy allows anonymous users to insert leads while keeping RLS enabled for security!**
