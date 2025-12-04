# Vercel Deployment Guide

## Overview
This guide will help you deploy the Mechanical (Robotics/AI) Branch Portal to Vercel, a fast and reliable hosting platform for modern web applications.

## Prerequisites

Before deploying, ensure you have:
- ✅ A Vercel account (sign up at [vercel.com](https://vercel.com))
- ✅ Git repository (GitHub, GitLab, or Bitbucket)
- ✅ Supabase project set up and running
- ✅ Environment variables ready (from `.env` file)

## Quick Start (Recommended)

### Method 1: Deploy via Vercel Dashboard (Easiest)

1. **Push code to Git repository**
   ```bash
   git add .
   git commit -m "Prepare for Vercel deployment"
   git push origin master
   ```

2. **Import project to Vercel**
   - Go to [vercel.com/new](https://vercel.com/new)
   - Click "Import Project"
   - Select your Git repository
   - Vercel will auto-detect Vite framework

3. **Configure environment variables**
   - In the "Environment Variables" section, add:
     ```
     VITE_APP_ID=app-806xhw354ao1
     VITE_SUPABASE_URL=https://exkusmdtpjszchwnngcs.supabase.co
     VITE_SUPABASE_ANON_KEY=your-supabase-anon-key
     VITE_API_ENV=production
     ```
   - Copy values from your `.env` file

4. **Deploy**
   - Click "Deploy"
   - Wait 2-3 minutes for build to complete
   - Your site will be live at `https://your-project.vercel.app`

### Method 2: Deploy via Vercel CLI

1. **Install Vercel CLI**
   ```bash
   npm install -g vercel
   ```

2. **Login to Vercel**
   ```bash
   vercel login
   ```

3. **Deploy**
   ```bash
   vercel
   ```
   - Follow the prompts
   - Vercel will ask about project settings
   - Accept defaults (already configured in `vercel.json`)

4. **Set environment variables**
   ```bash
   vercel env add VITE_APP_ID
   vercel env add VITE_SUPABASE_URL
   vercel env add VITE_SUPABASE_ANON_KEY
   vercel env add VITE_API_ENV
   ```

5. **Deploy to production**
   ```bash
   vercel --prod
   ```

## Configuration Files

### vercel.json
The project includes a `vercel.json` file with optimized settings:

```json
{
  "buildCommand": "npx vite build",
  "outputDirectory": "dist",
  "framework": "vite",
  "rewrites": [
    {
      "source": "/(.*)",
      "destination": "/index.html"
    }
  ]
}
```

**Key features:**
- ✅ SPA routing support (all routes redirect to index.html)
- ✅ Asset caching (1 year cache for static files)
- ✅ Security headers (X-Frame-Options, X-Content-Type-Options, X-XSS-Protection)
- ✅ Automatic framework detection
- ✅ Optimized build configuration

### Environment Variables

Required environment variables:

| Variable | Description | Example |
|----------|-------------|---------|
| `VITE_APP_ID` | Application identifier | `app-806xhw354ao1` |
| `VITE_SUPABASE_URL` | Supabase project URL | `https://xxx.supabase.co` |
| `VITE_SUPABASE_ANON_KEY` | Supabase anonymous key | `eyJhbGciOiJIUzI1NiIs...` |
| `VITE_API_ENV` | API environment | `production` |

## Step-by-Step Deployment Process

### Step 1: Prepare Your Repository

1. **Ensure all changes are committed**
   ```bash
   git status
   git add .
   git commit -m "Ready for deployment"
   ```

2. **Push to remote repository**
   ```bash
   git push origin master
   ```

### Step 2: Create Vercel Project

1. **Go to Vercel Dashboard**
   - Visit [vercel.com/dashboard](https://vercel.com/dashboard)
   - Click "Add New..." → "Project"

2. **Import Git Repository**
   - Select your Git provider (GitHub/GitLab/Bitbucket)
   - Authorize Vercel to access your repositories
   - Select the repository containing this project

3. **Configure Project**
   - **Project Name**: Choose a name (e.g., `robotics-portal`)
   - **Framework Preset**: Vite (auto-detected)
   - **Root Directory**: `./` (default)
   - **Build Command**: `npx vite build` (auto-configured from vercel.json)
   - **Output Directory**: `dist` (auto-configured from vercel.json)

### Step 3: Add Environment Variables

In the Vercel project settings:

1. **Navigate to Environment Variables section**

2. **Add each variable:**
   - Click "Add" for each variable
   - Enter name and value
   - Select environment: Production, Preview, Development (select all)

3. **Required variables:**
   ```
   Name: VITE_APP_ID
   Value: app-806xhw354ao1
   
   Name: VITE_SUPABASE_URL
   Value: https://exkusmdtpjszchwnngcs.supabase.co
   
   Name: VITE_SUPABASE_ANON_KEY
   Value: [your-anon-key-from-.env-file]
   
   Name: VITE_API_ENV
   Value: production
   ```

### Step 4: Deploy

1. **Click "Deploy"**
   - Vercel will start building your project
   - Build process takes 2-3 minutes

2. **Monitor build logs**
   - Watch for any errors
   - Build should complete successfully

3. **Access your site**
   - Once deployed, click "Visit" to see your live site
   - URL format: `https://your-project.vercel.app`

## Post-Deployment Configuration

### Custom Domain (Optional)

1. **Add custom domain**
   - Go to Project Settings → Domains
   - Click "Add"
   - Enter your domain (e.g., `robotics.university.edu`)

2. **Configure DNS**
   - Add CNAME record pointing to `cname.vercel-dns.com`
   - Or use Vercel nameservers

3. **SSL Certificate**
   - Automatically provisioned by Vercel
   - HTTPS enabled by default

### Automatic Deployments

Vercel automatically deploys when you push to Git:

- **Production**: Pushes to `master` or `main` branch
- **Preview**: Pushes to other branches or pull requests
- **Instant**: Deploys in 2-3 minutes

### Environment-Specific Settings

Configure different settings per environment:

1. **Production**
   - Uses production environment variables
   - Deployed from master branch
   - Custom domain (if configured)

2. **Preview**
   - Uses preview environment variables
   - Deployed from feature branches
   - Unique preview URL per branch

3. **Development**
   - Uses development environment variables
   - For local testing with Vercel CLI

## Supabase Configuration

### Update Supabase Settings

After deployment, update Supabase to allow your Vercel domain:

1. **Go to Supabase Dashboard**
   - Navigate to your project
   - Go to Authentication → URL Configuration

2. **Add Site URL**
   - Add your Vercel URL: `https://your-project.vercel.app`

3. **Add Redirect URLs**
   - Add: `https://your-project.vercel.app/**`
   - This allows authentication redirects

4. **Update CORS Settings**
   - Go to API Settings
   - Add your Vercel domain to allowed origins

## Build Optimization

### Performance Tips

1. **Enable Edge Network**
   - Vercel automatically uses global CDN
   - Assets cached at edge locations worldwide

2. **Image Optimization**
   - Use Vercel Image Optimization (optional)
   - Automatic WebP conversion

3. **Analytics**
   - Enable Vercel Analytics in project settings
   - Monitor performance and user behavior

### Build Settings

Optimized build configuration:

```json
{
  "buildCommand": "npx vite build",
  "outputDirectory": "dist",
  "installCommand": "npm install",
  "devCommand": "npx vite"
}
```

## Troubleshooting

### Common Issues

#### 1. Build Fails

**Error**: Build process fails on Vercel

**Solution**:
```bash
# Test build locally first
npx vite build

# Check for errors
npm run lint

# Fix any TypeScript errors
# Ensure all dependencies are in package.json
```

#### 2. Environment Variables Not Working

**Error**: Supabase connection fails

**Solution**:
- Verify all environment variables are set in Vercel
- Ensure variable names start with `VITE_`
- Redeploy after adding variables

#### 3. 404 Errors on Routes

**Error**: Direct navigation to routes shows 404

**Solution**:
- Verify `vercel.json` includes rewrite rules
- Check that `rewrites` section exists:
  ```json
  "rewrites": [
    { "source": "/(.*)", "destination": "/index.html" }
  ]
  ```

#### 4. Supabase Authentication Issues

**Error**: Login/signup not working

**Solution**:
- Add Vercel URL to Supabase allowed URLs
- Update redirect URLs in Supabase dashboard
- Check CORS settings

### Debug Mode

Enable verbose logging:

1. **In Vercel Dashboard**
   - Go to Deployments
   - Click on failed deployment
   - View build logs

2. **Locally with Vercel CLI**
   ```bash
   vercel --debug
   ```

## Monitoring and Maintenance

### Check Deployment Status

1. **Vercel Dashboard**
   - View all deployments
   - Check build logs
   - Monitor performance

2. **Deployment Notifications**
   - Email notifications for deployments
   - Slack/Discord integration available

### Update Deployment

To update your live site:

```bash
# Make changes
git add .
git commit -m "Update feature"
git push origin master

# Vercel automatically deploys
```

### Rollback

If something goes wrong:

1. **Go to Deployments**
2. **Find previous working deployment**
3. **Click "Promote to Production"**
4. **Instant rollback** (no rebuild needed)

## Performance Metrics

Expected performance after deployment:

- **Build Time**: 2-3 minutes
- **Deploy Time**: 30 seconds
- **Page Load**: < 1 second
- **Lighthouse Score**: 95-100
- **Global CDN**: Yes
- **HTTPS**: Automatic
- **Uptime**: 99.99%

## Security

### Best Practices

1. **Environment Variables**
   - Never commit `.env` to Git
   - Use Vercel environment variables
   - Rotate keys regularly

2. **Supabase Security**
   - Use Row Level Security (RLS)
   - Limit API key permissions
   - Monitor usage

3. **HTTPS**
   - Automatically enabled
   - Force HTTPS redirects
   - Modern TLS version

## Cost

### Vercel Pricing

- **Hobby Plan**: Free
  - Perfect for this project
  - Unlimited deployments
  - 100GB bandwidth/month
  - Automatic HTTPS

- **Pro Plan**: $20/month
  - Team collaboration
  - Advanced analytics
  - Priority support

## Continuous Integration

### Automatic Deployments

Vercel automatically:
- ✅ Builds on every push
- ✅ Runs tests (if configured)
- ✅ Deploys to preview URL
- ✅ Promotes to production (master branch)

### Preview Deployments

Every pull request gets:
- Unique preview URL
- Isolated environment
- Full functionality
- Easy testing before merge

## Support Resources

- **Vercel Documentation**: [vercel.com/docs](https://vercel.com/docs)
- **Vite on Vercel**: [vercel.com/docs/frameworks/vite](https://vercel.com/docs/frameworks/vite)
- **Supabase + Vercel**: [supabase.com/docs/guides/hosting/vercel](https://supabase.com/docs/guides/hosting/vercel)

## Checklist

Before deploying, ensure:

- [ ] All code committed and pushed to Git
- [ ] `.env` file values copied (don't commit `.env`)
- [ ] Supabase project is live and accessible
- [ ] `vercel.json` configuration file exists
- [ ] Build works locally (`npm run build`)
- [ ] No TypeScript errors (`npm run lint`)
- [ ] Environment variables documented
- [ ] Supabase URLs updated after deployment

## Quick Reference

### Essential Commands

```bash
# Deploy to Vercel
vercel

# Deploy to production
vercel --prod

# Check deployment status
vercel ls

# View logs
vercel logs

# Add environment variable
vercel env add VARIABLE_NAME

# Remove deployment
vercel rm deployment-url
```

### Important URLs

- **Vercel Dashboard**: https://vercel.com/dashboard
- **Your Supabase**: https://exkusmdtpjszchwnngcs.supabase.co
- **Deployment URL**: https://your-project.vercel.app (after deployment)

## Summary

Deploying to Vercel is simple:

1. **Push code to Git** → Vercel detects changes
2. **Import to Vercel** → Auto-configured with `vercel.json`
3. **Add environment variables** → Copy from `.env`
4. **Deploy** → Live in 2-3 minutes
5. **Update Supabase** → Add Vercel URL to allowed origins

**Your site will be live with:**
- ⚡ Lightning-fast global CDN
- 🔒 Automatic HTTPS
- 🚀 Automatic deployments
- 📊 Built-in analytics
- 🌍 99.99% uptime

**Ready to deploy!** 🎉
