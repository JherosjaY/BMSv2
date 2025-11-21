# 🚀 Render Deployment Setup - Elysia + Bun + Drizzle

Complete guide to deploy your backend on Render.com

---

## 📋 Render Form - Fill In These Values:

### Screen 1: New Web Service

**Source Code**
- ✅ Already connected: `JherosjaY / blotter-management-system`

**Service Type**
- ✅ Select: **Web Service**

**Name**
- ✅ Enter: `blotter-management-system`

**Project** (Optional)
- Leave blank or select existing project

**Language**
- ✅ Select: **Node** (Bun runs on Node runtime)

**Branch**
- ✅ Select: **main**

---

### Screen 2: Build & Deploy Configuration

**Region**
- ✅ Select: **Oregon (US West)** or closest to you

**Root Directory** (Optional)
- ✅ Enter: `backend-elysia`
- (This tells Render where your backend code is)

**Build Command**
- ✅ Enter: `bun install && bun run db:push`

**Start Command**
- ✅ Enter: `bun src/index.ts`

**Instance Type**
- ✅ Select: **Free** ($0/month) or **Starter** ($7/month)

---

### Screen 3: Environment Variables

**Add These Environment Variables:**

Click **+ Add Environment Variable** for each:

#### 1. DATABASE_URL
```
NAME: DATABASE_URL
VALUE: postgresql://user:password@ep-xyz.us-east-1.neon.tech/dbname?sslmode=require
```
(Replace with your actual Neon connection string)

#### 2. NODE_ENV
```
NAME: NODE_ENV
VALUE: production
```

#### 3. PORT
```
NAME: PORT
VALUE: 3000
```

#### 4. BFCACHE_ENABLED (Optional)
```
NAME: BFCACHE_ENABLED
VALUE: true
```

---

## ✅ Complete Configuration Summary

| Field | Value |
|-------|-------|
| **Service Type** | Web Service |
| **Name** | blotter-management-system |
| **Language** | Node |
| **Branch** | main |
| **Region** | Oregon (US West) |
| **Root Directory** | backend-elysia |
| **Build Command** | `bun install && bun run db:push` |
| **Start Command** | `bun src/index.ts` |
| **Plan** | Free or Starter |

---

## 🔧 Environment Variables

```
DATABASE_URL=postgresql://user:password@ep-xyz.us-east-1.neon.tech/dbname?sslmode=require
NODE_ENV=production
PORT=3000
```

---

## 🚀 After Deployment

### 1. Wait for Build
- Render will build and deploy
- Check logs for "Server running"

### 2. Get Your Live URL
- Format: `https://blotter-management-system.onrender.com`
- Or: `https://YOUR_SERVICE_NAME.onrender.com`

### 3. Test Your API
```bash
curl https://blotter-management-system.onrender.com/health
```

### 4. Update Android App
In your `ApiClient.kt`:
```kotlin
private const val BASE_URL = "https://blotter-management-system.onrender.com/"
```

---

## 📝 Important Notes

### Bun on Render
- ✅ Render supports Bun natively
- ✅ Bun is faster than Node.js
- ✅ No special configuration needed

### Drizzle ORM
- ✅ `bun run db:push` will auto-migrate
- ✅ Tables created automatically
- ✅ No manual SQL needed

### Cold Starts
- Free tier: ~30 second cold start
- Starter tier: ~5 second cold start
- Paid tier: Always warm

### Database Connection
- ✅ Neon PostgreSQL auto-connects
- ✅ SSL mode required (already in connection string)
- ✅ Connection pooling enabled

---

## 🆘 Troubleshooting

### Build Fails: "bun: command not found"
**Solution**: Render should auto-detect Bun. If not:
- Change Language to: **Node**
- Build Command: `npm install && npm run db:push`
- Start Command: `npm start`

### Database Connection Error
**Solution**:
- Verify DATABASE_URL is correct
- Check Neon database is running
- Ensure SSL mode is enabled

### Port Already in Use
**Solution**:
- Render manages ports automatically
- Don't hardcode port in code
- Use `process.env.PORT || 3000`

### Service Won't Start
**Solution**:
- Check logs in Render dashboard
- Verify all environment variables are set
- Check database connection

---

## 📊 Monitoring

After deployment:
1. Go to Render dashboard
2. Select your service
3. Check **Logs** tab
4. Monitor **Metrics** tab
5. Set up alerts (optional)

---

## 🎉 You're Ready!

Just fill in the form with the values above and click **Deploy Web Service**!

Your Blotter Management System will be live in 2-5 minutes! 🚀

---

**Your Live URL**: `https://blotter-management-system.onrender.com`

**Status**: ✅ Ready for Production
