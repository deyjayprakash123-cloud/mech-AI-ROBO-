# Quick Vercel Deployment Guide

## 🚀 Deploy in 5 Minutes

### Prerequisites
- Git repository (GitHub, GitLab, or Bitbucket)
- Vercel account (free at [vercel.com](https://vercel.com))
- Environment variables from `.env` file

### Step 1: Push to Git
```bash
git add .
git commit -m "Ready for Vercel deployment"
git push origin master
```

### Step 2: Import to Vercel
1. Go to [vercel.com/new](https://vercel.com/new)
2. Click "Import Project"
3. Select your repository
4. Vercel auto-detects Vite framework ✅

### Step 3: Add Environment Variables
In Vercel dashboard, add these variables:

```
VITE_APP_ID=app-806xhw354ao1
VITE_SUPABASE_URL=https://exkusmdtpjszchwnngcs.supabase.co
VITE_SUPABASE_ANON_KEY=[copy-from-.env-file]
VITE_API_ENV=production
```

**Important**: Copy the `VITE_SUPABASE_ANON_KEY` value from your `.env` file!

### Step 4: Deploy
1. Click "Deploy"
2. Wait 2-3 minutes
3. Your site is live! 🎉

### Step 5: Update Supabase
1. Go to [Supabase Dashboard](https://supabase.com/dashboard)
2. Navigate to: Authentication → URL Configuration
3. Add your Vercel URL: `https://your-project.vercel.app`
4. Add redirect URL: `https://your-project.vercel.app/**`

## ✅ That's It!

Your site is now live with:
- ⚡ Global CDN
- 🔒 Automatic HTTPS
- 🚀 Auto-deployments on Git push
- 📊 Built-in analytics

## 📚 Need More Help?

- **Detailed Guide**: See [VERCEL_DEPLOYMENT.md](./VERCEL_DEPLOYMENT.md)
- **Checklist**: See [DEPLOYMENT_CHECKLIST.md](./DEPLOYMENT_CHECKLIST.md)
- **Vercel Docs**: [vercel.com/docs](https://vercel.com/docs)

## 🔧 Configuration Files

This project includes:
- ✅ `vercel.json` - Vercel configuration
- ✅ `.vercelignore` - Files to exclude
- ✅ `.env.example` - Environment variables template

## 🎯 Build Configuration

The project uses:
- **Build Command**: `npx vite build`
- **Output Directory**: `dist`
- **Framework**: Vite (React + TypeScript)

All configured automatically via `vercel.json`!

## 🐛 Troubleshooting

### Build Fails?
```bash
# Test locally first
npx vite build
```

### Environment Variables Not Working?
- Ensure all variables start with `VITE_`
- Redeploy after adding variables
- Check Vercel dashboard for typos

### 404 on Routes?
- `vercel.json` handles this automatically
- Ensure file exists in repository

## 📞 Support

If you encounter issues:
1. Check build logs in Vercel dashboard
2. Review [VERCEL_DEPLOYMENT.md](./VERCEL_DEPLOYMENT.md)
3. Test build locally: `npx vite build`

---

**Happy Deploying!** 🚀
