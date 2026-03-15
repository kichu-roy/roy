# GitHub Pages & Actions Setup Guide

This guide walks you through setting up your resume website with GitHub Pages and GitHub Actions for automated deployment.

## 📋 Prerequisites

- GitHub account (free at https://github.com)
- Git installed on your computer
- A code editor (VS Code recommended)

## ✅ Step-by-Step Setup

### Step 1: Verify Your Repository Configuration

1. Go to your GitHub repository: `https://github.com/kichu-roy/roy`
2. Click **Settings** (top right)
3. Scroll down to **Pages** section

### Step 2: Enable GitHub Pages

1. In **Settings → Pages**, you should see:
   - **Build and deployment**: Select "Deploy from a branch"
   - **Branch**: Select `main` (or your default branch)
   - **Folder**: Select `/ (root)`

2. Click **Save**

3. You'll see a blue box confirming: "Your site is live at `https://kichu-roy.github.io/roy/`"

### Step 3: Verify GitHub Actions Workflow

1. Go to **Actions** tab in your repository
2. Look for workflow named "Deploy to GitHub Pages"
3. You should see recent workflow runs

### Step 4: Push Changes to Trigger Deployment

```bash
# Navigate to your project
cd path/to/roy

# Add all files
git add .

# Commit changes
git commit -m "Create professional resume website with GitHub Pages"

# Push to GitHub
git push origin main
```

### Step 5: Monitor Deployment

1. Go to **Actions** tab
2. Watch the workflow run
3. When it shows ✅, your site is live!

## 🌐 Access Your Website

After deployment, visit:

- **GitHub Pages**: https://kichu-roy.github.io/roy/
- **GitHub Repo**: https://github.com/kichu-roy/roy
- **GitHub Profile**: https://github.com/kichu-roy

## 🔄 How GitHub Actions Works

```yaml
Trigger: You push code to GitHub
    ↓
Workflow "Deploy to GitHub Pages" starts
    ↓
1. Checkout repository
2. Configure Pages environment
3. Upload files as artifact
4. Deploy to GitHub Pages
    ↓
Your changes go LIVE in ~30 seconds!
```

## 📝 Updating Your Resume

Every time you make changes:

```bash
# Edit index.html with your information

# Stage changes
git add index.html

# Commit
git commit -m "Update resume with new experience"

# Push (this triggers automatic deployment!)
git push origin main

# Visit https://kichu-roy.github.io/roy/ to see changes
```

## 🎯 GitHub Pages Features

### Custom Domain (Optional)

To use your own domain instead of `github.io`:

1. In **Settings → Pages**
2. Under **Custom domain**, enter your domain
3. Add DNS records to your domain provider
4. GitHub will verify and enable HTTPS

### Branch Deployment

The workflow is configured to deploy from:

- `main` branch - your primary deployment
- `resume` branch - alternative branch if created

### Automatic HTTPS

✅ Automatically enabled (no configuration needed)

## 🐛 Troubleshooting Deployment

### Site Not Updating After Push

```bash
# Clear browser cache: Ctrl+Shift+Delete (Windows) or Cmd+Shift+Delete (Mac)
# Or do a hard refresh: Ctrl+F5 (Windows) or Cmd+Shift+R (Mac)
# Wait 1-2 minutes for GitHub Actions to complete
```

### Check Workflow Status

1. Go to **Actions** tab
2. Click on latest workflow run
3. Check for ❌ errors
4. Common issues:
   - HTML syntax errors
   - Missing files
   - Branch configuration

### Force Rebuild

```bash
# Make an empty commit to trigger workflow
git commit --allow-empty -m "Trigger rebuild"
git push origin main
```

### Reset GitHub Pages

1. Go to **Settings → Pages**
2. Change branch to a different branch (e.g., gh-pages)
3. Change it back to `main`
4. Trigger a new push

## 📊 Workflow File Breakdown

File: `.github/workflows/deploy.yml`

```yaml
name: Deploy to GitHub Pages # Workflow name

on:
  push:
    branches:
      - main # Trigger on push to main
      - resume # Also trigger on push to resume

jobs:
  deploy:
    runs-on: ubuntu-latest # Use Ubuntu runner

    permissions:
      pages: write # Permission to write to Pages
      contents: read
      id-token: write

    steps:
      - uses: actions/checkout@v4 # Step 1: Get your code
      - uses: actions/configure-pages@v4 # Step 2: Setup Pages
      - uses: actions/upload-pages-artifact@v3 # Step 3: Upload files
      - uses: actions/deploy-pages@v2 # Step 4: Deploy!
```

## 🚀 Advanced Configuration

### Setup Development Branch

For testing before publishing:

```bash
# Create dev branch
git checkout -b develop

# Make changes and test locally
# Then merge to main when ready
git checkout main
git merge develop
git push origin main
```

### Setup Multiple Sites

Create workflow for different branches:

```yaml
on:
  push:
    branches:
      - main # Deploy from main
      - staging # Deploy from staging to different URL
```

## 📱 Testing Locally

### Quick Test

```bash
# Use Python built-in server
python -m http.server 8000

# Open browser to http://localhost:8000
```

### Using Node.js

```bash
# Install http-server
npm install -g http-server

# Run server
http-server

# Opens at http://localhost:8080
```

## 🔒 Repository Settings

### Ensure Public Repository

GitHub Pages only works with public repositories (for free tier)

Settings → General → Repository visibility → **Public**

### Branch Protection (Optional)

For extra safety:

1. Settings → Branches
2. Add rule for `main` branch
3. Require pull request reviews before merging
4. Dismiss stale PR approvals when new commits pushed

## 📈 Monitor Your Site

### GitHub Actions Insights

- **Actions** tab → See all workflow runs
- Click any run to see detailed logs
- Check execution time and status

### View Deployment History

1. **Settings → Pages**
2. Scroll to "Deployment history"
3. See all past deployments with timestamps

## 🎓 Learning Resources

- [GitHub Pages Docs](https://docs.github.com/en/pages)
- [GitHub Actions Docs](https://docs.github.com/en/actions)
- [YAML Syntax](https://yaml.org/spec/)
- [HTML & CSS Guide](https://developer.mozilla.org/en-US/docs/Web/Guide)

## ✨ Tips & Best Practices

1. **Commit Messages**: Use clear, descriptive messages

   ```
   ✅ Good: "Add new project experience"
   ❌ Bad: "update"
   ```

2. **Test Before Push**: Verify changes locally first

3. **Keep Files Organized**: Use proper directory structure

4. **Update Regularly**: Keep resume current

5. **Use Branches**: For major changes, use feature branches

6. **Link to Previous Work**: Reference your projects

7. **Optimize for Mobile**: Test on different devices

## 🎉 You're All Set!

Your resume website is now:

- ✅ Live on GitHub Pages
- ✅ Automatically deployed with GitHub Actions
- ✅ Accessible from anywhere (https://kichu-roy.github.io/roy/)
- ✅ Updated instantly on every push
- ✅ Professional and modern design

**Start making changes and watch them deploy automatically!**

---

**Questions?** Check the troubleshooting section or visit GitHub Docs.

**Last Updated**: March 2026
