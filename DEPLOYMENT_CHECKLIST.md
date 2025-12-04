# Vercel Deployment Checklist

## Pre-Deployment

### 1. Code Preparation
- [ ] All changes committed to Git
- [ ] Code pushed to remote repository (GitHub/GitLab/Bitbucket)
- [ ] No uncommitted changes (`git status` is clean)
- [ ] Build works locally (test with `npx vite build`)

### 2. Environment Variables Ready
Copy these values from your `.env` file:

```bash
VITE_APP_ID=app-806xhw354ao1
VITE_SUPABASE_URL=https://exkusmdtpjszchwnngcs.supabase.co
VITE_SUPABASE_ANON_KEY=[your-key-from-.env-file]
VITE_API_ENV=production
```

- [ ] Environment variables documented
- [ ] Supabase URL confirmed
- [ ] Supabase anon key copied
- [ ] App ID noted

### 3. Supabase Configuration
- [ ] Supabase project is live
- [ ] Database tables created (via migrations)
- [ ] Storage buckets configured
- [ ] RLS policies set up
- [ ] Test data added (if needed)

## Deployment Steps

### Method 1: Vercel Dashboard (Recommended)

#### Step 1: Import Project
- [ ] Go to [vercel.com/new](https://vercel.com/new)
- [ ] Click "Import Project"
- [ ] Connect Git provider (GitHub/GitLab/Bitbucket)
- [ ] Select repository
- [ ] Vercel auto-detects Vite framework

#### Step 2: Configure Settings
- [ ] Project name: `robotics-portal` (or your choice)
- [ ] Framework: Vite (auto-detected)
- [ ] Root directory: `./` (default)
- [ ] Build command: `npx vite build` (from vercel.json)
- [ ] Output directory: `dist` (from vercel.json)

#### Step 3: Add Environment Variables
Add each variable in Vercel dashboard:

- [ ] `VITE_APP_ID` = `app-806xhw354ao1`
- [ ] `VITE_SUPABASE_URL` = `https://exkusmdtpjszchwnngcs.supabase.co`
- [ ] `VITE_SUPABASE_ANON_KEY` = `[your-anon-key]`
- [ ] `VITE_API_ENV` = `production`

**Important**: Select all environments (Production, Preview, Development)

#### Step 4: Deploy
- [ ] Click "Deploy" button
- [ ] Wait 2-3 minutes for build
- [ ] Check build logs for errors
- [ ] Verify deployment success

### Method 2: Vercel CLI

#### Step 1: Install CLI
```bash
npm install -g vercel
```
- [ ] Vercel CLI installed

#### Step 2: Login
```bash
vercel login
```
- [ ] Logged in to Vercel

#### Step 3: Deploy
```bash
vercel
```
- [ ] Follow prompts
- [ ] Accept default settings
- [ ] Deployment complete

#### Step 4: Add Environment Variables
```bash
vercel env add VITE_APP_ID
vercel env add VITE_SUPABASE_URL
vercel env add VITE_SUPABASE_ANON_KEY
vercel env add VITE_API_ENV
```
- [ ] All environment variables added

#### Step 5: Deploy to Production
```bash
vercel --prod
```
- [ ] Production deployment complete

## Post-Deployment

### 1. Verify Deployment
- [ ] Visit deployment URL (e.g., `https://your-project.vercel.app`)
- [ ] Homepage loads correctly
- [ ] Navigation works (test all menu items)
- [ ] Images load properly
- [ ] Animations work smoothly

### 2. Test Core Features
- [ ] Admin login works
- [ ] Dashboard displays correctly
- [ ] Can create/edit/delete content
- [ ] Image uploads work
- [ ] Logo upload and compression works
- [ ] Forms submit successfully
- [ ] Database operations work

### 3. Test All Pages
- [ ] Home page
- [ ] About Us page
- [ ] Academics page
- [ ] Achievements page
- [ ] News page
- [ ] Students page
- [ ] Alumni page
- [ ] Gallery page
- [ ] Contact page
- [ ] Admin panel

### 4. Update Supabase Settings
- [ ] Go to Supabase Dashboard
- [ ] Navigate to Authentication → URL Configuration
- [ ] Add Site URL: `https://your-project.vercel.app`
- [ ] Add Redirect URLs: `https://your-project.vercel.app/**`
- [ ] Update CORS settings (API Settings)
- [ ] Add Vercel domain to allowed origins

### 5. Performance Check
- [ ] Page loads in < 2 seconds
- [ ] Images load quickly
- [ ] No console errors
- [ ] Mobile responsive
- [ ] Works on different browsers

### 6. Security Check
- [ ] HTTPS enabled (automatic)
- [ ] Environment variables not exposed
- [ ] No sensitive data in client code
- [ ] RLS policies working
- [ ] Admin routes protected

## Optional Enhancements

### Custom Domain
- [ ] Purchase domain (if needed)
- [ ] Add domain in Vercel project settings
- [ ] Configure DNS records
- [ ] Wait for SSL certificate (automatic)
- [ ] Update Supabase allowed URLs

### Analytics
- [ ] Enable Vercel Analytics
- [ ] Set up monitoring
- [ ] Configure error tracking

### Notifications
- [ ] Set up deployment notifications
- [ ] Configure Slack/Discord integration (optional)
- [ ] Email notifications enabled

## Troubleshooting

### Build Fails
- [ ] Check build logs in Vercel dashboard
- [ ] Verify all dependencies installed
- [ ] Test build locally: `npx vite build`
- [ ] Check for TypeScript errors
- [ ] Verify environment variables set

### Environment Variables Not Working
- [ ] Verify variable names start with `VITE_`
- [ ] Check variables set for correct environment
- [ ] Redeploy after adding variables
- [ ] Clear cache and redeploy

### 404 Errors on Routes
- [ ] Verify `vercel.json` exists
- [ ] Check rewrite rules configured
- [ ] Ensure SPA routing enabled

### Supabase Connection Issues
- [ ] Verify Supabase URL correct
- [ ] Check anon key is valid
- [ ] Confirm Vercel URL in Supabase allowed origins
- [ ] Test Supabase connection locally

### Images Not Loading
- [ ] Check Supabase storage bucket public
- [ ] Verify image URLs correct
- [ ] Test image compression feature
- [ ] Check CORS settings

## Maintenance

### Regular Updates
- [ ] Monitor deployment status
- [ ] Check error logs weekly
- [ ] Update dependencies monthly
- [ ] Review performance metrics

### Backup Strategy
- [ ] Database backups (Supabase automatic)
- [ ] Code in Git repository
- [ ] Environment variables documented
- [ ] Deployment history in Vercel

## Quick Reference

### Important URLs
- **Vercel Dashboard**: https://vercel.com/dashboard
- **Supabase Dashboard**: https://supabase.com/dashboard
- **Your Deployment**: https://your-project.vercel.app
- **Git Repository**: [your-repo-url]

### Essential Commands
```bash
# Deploy to Vercel
vercel

# Deploy to production
vercel --prod

# Check status
vercel ls

# View logs
vercel logs

# Add environment variable
vercel env add VARIABLE_NAME
```

### Environment Variables
```
VITE_APP_ID=app-806xhw354ao1
VITE_SUPABASE_URL=https://exkusmdtpjszchwnngcs.supabase.co
VITE_SUPABASE_ANON_KEY=[from-.env-file]
VITE_API_ENV=production
```

## Success Criteria

Deployment is successful when:
- ✅ Site is live and accessible
- ✅ All pages load correctly
- ✅ Admin panel works
- ✅ Database operations function
- ✅ Images and assets load
- ✅ No console errors
- ✅ Mobile responsive
- ✅ HTTPS enabled
- ✅ Performance is good (< 2s load time)

## Support

If you need help:
1. Check [VERCEL_DEPLOYMENT.md](./VERCEL_DEPLOYMENT.md) for detailed guide
2. Review Vercel documentation: https://vercel.com/docs
3. Check Supabase docs: https://supabase.com/docs
4. Review build logs in Vercel dashboard

---

**Ready to deploy!** 🚀

Follow this checklist step by step, and your site will be live in minutes!
