# 🚀 Quick Start - Vercel Deployment

## Deploy Your Site in 5 Minutes

### Step 1: Environment Variables
Copy these from your `.env` file:

```bash
VITE_APP_ID=app-806xhw354ao1
VITE_SUPABASE_URL=https://exkusmdtpjszchwnngcs.supabase.co
VITE_SUPABASE_ANON_KEY=[COPY FROM .env FILE]
VITE_API_ENV=production
```

### Step 2: Push to Git
```bash
git push origin master
```

### Step 3: Deploy to Vercel
1. Go to: https://vercel.com/new
2. Click "Import Project"
3. Select your repository
4. Add environment variables (from Step 1)
5. Click "Deploy"

### Step 4: Update Supabase
1. Go to: https://supabase.com/dashboard
2. Select your project
3. Go to: Authentication → URL Configuration
4. Add your Vercel URL: `https://your-project.vercel.app`
5. Add redirect: `https://your-project.vercel.app/**`

## ✅ Done!

Your site is now live at: `https://your-project.vercel.app`

## 📚 Need More Help?

- **Quick Guide**: [VERCEL_README.md](./VERCEL_README.md)
- **Detailed Guide**: [VERCEL_DEPLOYMENT.md](./VERCEL_DEPLOYMENT.md)
- **Checklist**: [DEPLOYMENT_CHECKLIST.md](./DEPLOYMENT_CHECKLIST.md)
- **Summary**: [DEPLOYMENT_SUMMARY.md](./DEPLOYMENT_SUMMARY.md)

## 🔧 Configuration Files

All ready to use:
- ✅ `vercel.json` - Build configuration
- ✅ `.vercelignore` - Exclude files
- ✅ `.env.example` - Environment template

## ⚡ Features Enabled

- Global CDN
- Automatic HTTPS
- SPA Routing
- Security Headers
- Asset Caching
- Auto-deployments

## 🎯 What's Configured

- **Build**: `npx vite build`
- **Output**: `dist`
- **Framework**: Vite (auto-detected)
- **Routing**: SPA (all routes work)
- **Security**: Headers configured
- **Performance**: Optimized caching

---

**Ready to deploy!** 🎉
