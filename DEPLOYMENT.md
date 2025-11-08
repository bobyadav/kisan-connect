# KisanConnect 2.0 Deployment Guide

## Vercel Deployment

### Prerequisites
- Vercel account
- GitHub repository
- MongoDB Atlas account

### Steps

1. **Push to GitHub**
   - Initialize git: `git init`
   - Add remote: `git remote add origin <your-repo-url>`
   - Commit and push: `git add . && git commit -m "Initial commit" && git push`

2. **Connect to Vercel**
   - Go to https://vercel.com/dashboard
   - Click "Add New" → "Project"
   - Import your GitHub repository
   - Select Next.js as framework

3. **Configure Environment Variables**
   - In Vercel project settings, add:
     - `MONGODB_URI` - Your MongoDB Atlas connection string
     - `JWT_SECRET` - Generate a strong secret key
     - `CRON_SECRET` - Secret for cron jobs
     - `NEXT_PUBLIC_API_URL` - Your Vercel domain

4. **Deploy**
   - Click "Deploy"
   - Wait for build to complete
   - Your site is live!

### Setting Up Cron Jobs

Use a cron service like EasyCron or GitHub Actions to trigger:

\`\`\`bash
# Update market prices hourly
curl -X POST https://your-domain.vercel.app/api/cron/market-prices \
  -H "x-cron-secret: your-cron-secret"

# Update news hourly
curl -X POST https://your-domain.vercel.app/api/cron/news \
  -H "x-cron-secret: your-cron-secret"
\`\`\`

## Environment Variables Needed

\`\`\`
MONGODB_URI=mongodb+srv://...
JWT_SECRET=your-secret-key
CRON_SECRET=your-cron-secret
NEXT_PUBLIC_API_URL=https://your-domain.vercel.app
SMTP_HOST=smtp.gmail.com
SMTP_USER=your-email
SMTP_PASS=your-app-password
\`\`\`

## Database Setup

1. Create MongoDB Atlas cluster
2. Get connection string
3. Run: `npm run init-db`
4. Run: `npm run seed`

## Monitoring

- Check Vercel Analytics
- Monitor MongoDB metrics
- Set up error tracking
- Enable performance monitoring
