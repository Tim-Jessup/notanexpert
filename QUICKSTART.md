# Quick Start Guide for notanexpert.fyi

## What you have

A complete Hugo static site ready to deploy. Everything is configured for your domain: notanexpert.fyi

## Next steps

### 1. Download and extract this site

Download the `notanexpert-site` folder to your computer.

### 2. Install Hugo (one time only)

**macOS:**
Open Terminal and run:
```bash
brew install hugo
```

**Windows:**
Open PowerShell as Administrator and run:
```bash
choco install hugo-extended
```
(If you don't have Chocolatey, get it from https://chocolatey.org/)

**Linux:**
```bash
sudo snap install hugo
```

Verify installation:
```bash
hugo version
```

### 3. Preview your site locally

Open Terminal/Command Prompt, navigate to the site folder and run:
```bash
cd path/to/notanexpert-site
hugo server -D
```

Open your browser to: http://localhost:1313

You should see your site! Try editing the markdown files in `content/` - the site updates automatically.

### 4. Deploy to GitHub Pages (FREE hosting)

**A. Create GitHub account** (if you don't have one)
- Go to https://github.com
- Sign up for free

**B. Create repository**
- Click "New repository"
- Name it: `notanexpert-site` (or anything you like)
- Make it Public
- Don't initialize with README (we have one)
- Click "Create repository"

**C. Upload your site**
In your terminal, in the notanexpert-site folder:
```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/notanexpert-site.git
git push -u origin main
```
(Replace YOUR-USERNAME with your GitHub username)

**D. Enable GitHub Pages**
1. Go to your repository on GitHub
2. Click "Settings" tab
3. Click "Pages" in left sidebar
4. Under "Build and deployment":
   - Source: select "GitHub Actions"
5. Wait a few minutes for the action to complete

Your site is now live at: `https://YOUR-USERNAME.github.io/notanexpert-site/`

### 5. Connect your custom domain (notanexpert.fyi)

**A. In GitHub:**
1. Repository Settings → Pages
2. Under "Custom domain" enter: `notanexpert.fyi`
3. Click Save
4. Wait for DNS check

**B. In your domain registrar** (where you bought notanexpert.fyi):

Add these DNS records:

**A records** (for apex domain):
```
Type: A    Name: @    Value: 185.199.108.153
Type: A    Name: @    Value: 185.199.109.153
Type: A    Name: @    Value: 185.199.110.153
Type: A    Name: @    Value: 185.199.111.153
```

**CNAME record** (for www):
```
Type: CNAME    Name: www    Value: YOUR-USERNAME.github.io
```

**C. Wait for DNS to propagate** (5 minutes to 24 hours, usually quick)

Visit https://notanexpert.fyi - your site should be live!

## Making changes

### Edit existing content
1. Edit markdown files in `content/` folder
2. Save the file
3. If `hugo server` is running, see changes instantly
4. When happy, commit and push:
   ```bash
   git add .
   git commit -m "Updated content"
   git push
   ```
5. GitHub automatically rebuilds and deploys (takes 1-2 minutes)

### Add new content

**New project:**
```bash
hugo new projects/my-new-project.md
```

**New tool:**
```bash
hugo new tools/my-new-tool.md
```

**New note:**
```bash
hugo new notes/my-learning-note.md
```

Then edit the created file, save, commit, and push.

### Customize appearance

Edit `themes/simple-portfolio/static/css/style.css` to change colors, fonts, spacing, etc.

## Troubleshooting

**"hugo: command not found"**
- Hugo isn't installed or not in your PATH
- Try reinstalling Hugo

**Changes not showing on live site**
- Check GitHub Actions tab in your repository
- Look for failed builds (red X)
- Most common issue: syntax error in markdown front matter

**Domain not working**
- DNS takes time to propagate
- Check DNS settings in your registrar
- Verify custom domain is set in GitHub Pages settings

## Cost

- Domain: ~$10-15/year (you already paid for this)
- GitHub Pages hosting: **FREE**
- Total ongoing cost: Just the domain renewal

## Resources

- **Hugo docs:** https://gohugo.io/documentation/
- **Markdown guide:** https://www.markdownguide.org/
- **GitHub Pages docs:** https://docs.github.com/en/pages
- **Your site examples:** Look in `content/` folder for examples

## Questions?

The README.md file in the site folder has more detailed information about customization and advanced features.

Good luck with notanexpert.fyi! 🚀
