# 🚀 Neon PostgreSQL Setup - 5 Minutes

Quick setup guide for Neon database

---

## Step 1: Create Neon Account

1. Go to **https://neon.tech**
2. Click **Sign Up**
3. Use GitHub, Google, or email
4. Verify email

---

## Step 2: Create New Project

1. Click **New Project**
2. **Project name**: `blotter-management-db`
3. **Database name**: `blotter` (default is fine)
4. **Region**: Select **Singapore** (closest to PH)
5. **PostgreSQL version**: 15 (default)
6. Click **Create project**

---

## Step 3: Get Connection String

1. After project created, you'll see the connection string
2. Or go to **Connection string** tab
3. Copy the full connection string:

```
postgresql://user:password@ep-xyz.us-east-1.neon.tech/dbname?sslmode=require
```

**SAVE THIS!** You need it for Render!

---

## Step 4: Create Tables (Optional)

Your backend (Drizzle ORM) will auto-create tables, so you don't need to do this manually.

But if you want to pre-create them:

1. Go to **SQL Editor** in Neon
2. Run the schema SQL (from your backend)
3. Done!

---

## Step 5: Add to Render

1. Go to Render dashboard
2. Select your service
3. Go to **Environment**
4. Add/Update `DATABASE_URL`:
   ```
   DATABASE_URL = postgresql://user:password@ep-xyz.us-east-1.neon.tech/dbname?sslmode=require
   ```
5. Click **Save**
6. Redeploy

---

## ✅ Done!

Your Neon database is ready! 🎉

**Your connection string**: `postgresql://...`

---

**Next**: Push backend submodule and redeploy on Render!
