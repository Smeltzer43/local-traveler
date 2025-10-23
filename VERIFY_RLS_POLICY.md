# 🚨 URGENT: Verify RLS Policy for Leads Table

## **The Issue**
Authentication is working, but leads are NOT being saved to the database. This is likely an RLS (Row Level Security) policy issue.

## **🔍 How to Check Your RLS Policy**

### **Step 1: Go to Supabase Dashboard**
1. Go to: https://supabase.com/dashboard
2. Click on your project: `jxytzukoqwmcrlldsbpo`
3. Go to **Authentication** → **Policies**

### **Step 2: Find the Leads Table Policy**
1. Look for **`public.leads`** in the policies list
2. Click on it to see the policy details

### **Step 3: Verify Policy Settings**
**Your policy should look like this:**
```sql
create policy "Allow anonymous users to insert leads"
on "public"."leads"
as PERMISSIVE
for INSERT
to anon
using (true);
```

### **Step 4: Check These Key Points**
- ✅ **Target Role**: Should be `anon` (NOT `authenticated`)
- ✅ **Operation**: Should be `INSERT`
- ✅ **Policy Definition**: Should be `true`
- ✅ **Status**: Should be **enabled/active**

## **🚨 Common Issues**

### **Issue 1: Wrong Target Role**
- ❌ **Wrong**: `to authenticated`
- ✅ **Correct**: `to anon`

### **Issue 2: Policy Disabled**
- Check if the policy is **enabled/active**
- Toggle should be **ON**

### **Issue 3: Wrong Operation**
- Should be **INSERT** only
- Not SELECT, UPDATE, or DELETE

## **🔧 Quick Fix**

### **If Policy is Wrong:**
1. **Delete the existing policy**
2. **Create a new one** with these exact settings:
   - **Name**: `Allow anonymous users to insert leads`
   - **Table**: `public.leads`
   - **Operation**: `INSERT`
   - **Target Role**: `anon`
   - **Policy Definition**: `true`

### **Alternative: Disable RLS Temporarily**
1. Go to **Table Editor** → **leads** table
2. **Disable RLS** (toggle off)
3. **Test your form**
4. **Re-enable RLS** after testing

## **🧪 Test After Fix**
1. **Submit popup form**
2. **Click magic link**
3. **Check browser console** for "RLS test result"
4. **Check leads table** in Supabase
5. **Verify lead appears**

---

**The RLS policy is the most likely cause of this issue!** 🎯
