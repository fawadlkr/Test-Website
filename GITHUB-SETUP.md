# GitHub Setup & Deployment Guide

Your Pak-Composing landing page is ready to deploy! Follow these steps to push it to GitHub and live it on Netlify.

## Prerequisites

Make sure you have:
1. **Git installed** - Download from [git-scm.com](https://git-scm.com/download/win)
2. **GitHub account** - Sign up at [github.com](https://github.com)
3. **Netlify account** - Sign up at [netlify.com](https://netlify.com)

## Step 1: Install Git (Windows)

1. Download Git from https://git-scm.com/download/win
2. Run the installer and follow the default options
3. Restart your terminal/PowerShell
4. Verify installation by running:
```powershell
git --version
```

## Step 2: Configure Git

Run these commands in PowerShell:

```powershell
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

Replace with your actual name and GitHub email.

## Step 3: Initialize Repository Locally

Navigate to your project folder and initialize git:

```powershell
cd "C:\Users\tasir\Desktop\Pak-composing"
git init
git add .
git commit -m "Initial commit: Pak-Composing Center landing page"
git branch -M main
```

## Step 4: Create GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. **Repository name**: `pak-composing` (or your preferred name)
3. **Description**: "Professional landing page for Pak-Composing Center"
4. Choose **Public** (for Netlify deployment)
5. Click **Create repository**
6. **Do NOT** initialize with README (we already have one)

## Step 5: Connect & Push to GitHub

GitHub will show you commands to push. In PowerShell, run:

```powershell
cd "C:\Users\tasir\Desktop\Pak-composing"
git remote add origin https://github.com/YOUR_USERNAME/pak-composing.git
git push -u origin main
```

Replace `YOUR_USERNAME` with your actual GitHub username.

**Note**: You may be prompted to authenticate. Use one of these options:
- **Option A**: GitHub CLI (easiest) - follow the prompt
- **Option B**: Personal Access Token - generate one at [github.com/settings/tokens](https://github.com/settings/tokens)
- **Option C**: SSH Key - set up SSH following [GitHub's guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

## Step 6: Deploy to Netlify

### Method A: Through GitHub (Recommended - Auto-Deploy)

1. Go to [netlify.com](https://netlify.com) and sign in
2. Click **"Add new site"** → **"Import an existing project"**
3. Select **GitHub** and authorize Netlify
4. Choose your `pak-composing` repository
5. Click **"Deploy site"**
6. Netlify will assign you a live URL like: `https://your-site-name.netlify.app`

**Auto-deployment**: Every time you push to GitHub, Netlify automatically rebuilds and deploys your site!

### Method B: Through Netlify Drag & Drop (Manual)

1. Go to [netlify.com](https://netlify.com)
2. Drag and drop your project folder onto the Netlify dashboard
3. Your site goes live instantly

### Method C: Netlify CLI

```powershell
# Install Netlify CLI
npm install -g netlify-cli

# Login to Netlify
netlify login

# Deploy your site
netlify deploy --prod
```

## Step 7: Custom Domain (Optional)

1. After deployment, go to your Netlify site settings
2. Click **"Domain settings"**
3. Add a custom domain (e.g., `pakcomposing.com`)
4. Follow DNS configuration steps

## Verify Your Live Site

After deployment:
1. Visit your Netlify URL
2. Test all links and sections
3. Fill out the contact form to verify it works
4. Test on mobile devices
5. Check page load speed using [PageSpeed Insights](https://pagespeed.web.dev)

## Future Updates

Every time you want to update your site:

```powershell
# Make changes to your files
# Then commit and push:
git add .
git commit -m "Update: description of changes"
git push origin main
```

Netlify will automatically rebuild and deploy within seconds!

## Quick Command Reference

```powershell
# Check git status
git status

# View commit history
git log --oneline

# View remote URL
git remote -v

# Pull latest changes
git pull origin main

# Create a new branch for testing
git checkout -b feature/my-feature
git push -u origin feature/my-feature
```

## Troubleshooting

### Git not recognized?
- Restart PowerShell/Terminal after installing Git
- Or use Git Bash instead of PowerShell

### Authentication failed?
- Use a Personal Access Token instead of password
- Generate at: https://github.com/settings/tokens
- Select `repo` scope
- Use token as password when prompted

### Site not updating after push?
- Wait 1-2 minutes for Netlify build to complete
- Check Netlify deploy logs: site settings → "Deploys"
- Clear browser cache (Ctrl+Shift+Delete)

### Form not working on Netlify?
- Make sure form has `netlify` attribute in HTML, OR
- Set up Formspree integration (see README.md)

## Support Resources

- **Git Help**: https://git-scm.com/doc
- **GitHub Help**: https://docs.github.com
- **Netlify Docs**: https://docs.netlify.com
- **Markdown Guide**: https://www.markdownguide.org

---

**You're all set!** Your landing page is production-ready and waiting to go live. 🚀
