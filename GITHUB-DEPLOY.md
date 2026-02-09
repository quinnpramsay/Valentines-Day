# 🚀 GitHub + Netlify Deployment Guide

## Complete Setup Instructions

Follow these steps to deploy your Valentine's website from GitHub to Netlify.

---

## Step 1: Upload to GitHub

### Option A: Using GitHub Desktop (Easiest for Beginners)

1. **Download GitHub Desktop**
   - Go to [desktop.github.com](https://desktop.github.com)
   - Download and install

2. **Create Repository**
   - Open GitHub Desktop
   - Click "File" → "New Repository"
   - Name: `valentine-website` (or any name you like)
   - Local Path: Choose where to save
   - Click "Create Repository"

3. **Add Your Files**
   - Copy ALL files from this project into the new repository folder
   - **Important:** Make sure to include both custom images:
     - `first-no-image.png` (the "OHMYGODDDD" photo)
     - `celebration-image.png` (the celebration photo)
   - GitHub Desktop will show all files as changes

4. **Commit and Push**
   - In GitHub Desktop, write commit message: "Initial Valentine's website"
   - Click "Commit to main"
   - Click "Publish repository"
   - Choose "Public" or "Private" (either works)
   - Click "Publish Repository"

### Option B: Using Command Line (For Developers)

1. **Navigate to project folder**
   ```bash
   cd /path/to/valentine-website
   ```

2. **Initialize Git**
   ```bash
   git init
   git add .
   git commit -m "Initial Valentine's website"
   ```

3. **Create GitHub Repository**
   - Go to [github.com/new](https://github.com/new)
   - Repository name: `valentine-website`
   - Click "Create repository"

4. **Push to GitHub**
   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/valentine-website.git
   git branch -M main
   git push -u origin main
   ```

---

## Step 2: Deploy to Netlify

### A. Connect GitHub to Netlify

1. **Go to Netlify**
   - Visit [app.netlify.com](https://app.netlify.com)
   - Sign up or log in (can use GitHub account)

2. **Create New Site**
   - Click "Add new site" button
   - Select "Import an existing project"

3. **Connect GitHub**
   - Click "GitHub"
   - Authorize Netlify (if first time)
   - Select your repository: `valentine-website`

4. **Configure Build Settings**
   - Netlify auto-detects settings from `netlify.toml`
   - You should see:
     - **Build command:** (empty)
     - **Publish directory:** `.`
     - **Functions directory:** `netlify/functions`
   - Click "Deploy site"

5. **Wait for Deploy**
   - First deploy takes 30-60 seconds
   - Site will be live at: `https://random-name-12345.netlify.app`

---

## Step 3: Test Your Site

### Test the Flow

1. **Visit your site** at the Netlify URL
2. **Click "No"** - Image appears, heading changes to "No is not an option.", "Try Again" button shows (visible on screen)
3. **Click "Try Again"** - Returns to "Will you be my Valentine?", normal buttons appear
4. **Click "No" again** - "I said no is not an option." message appears briefly
5. **Click "No" third time** - Button starts moving with smooth, bouncy animations
6. **Try "No" again** - Button keeps moving playfully (impossible to click)
7. **Click "Yes"** - Should see:
   - ✨ Confetti animation
   - 💕 Custom message: "Hell fucking yea lets go, see you then!"
   - 🖼️ Custom celebration photo

---

## Step 4: Customize Your URL (Optional)

### Option A: Free Netlify Subdomain

1. In Netlify Dashboard → "Site settings" → "Site details"
2. Click "Change site name"
3. Enter custom name: `quinn-valentine` (or any available name)
4. New URL: `https://quinn-valentine.netlify.app`

### Option B: Custom Domain (Advanced)

1. Buy domain (e.g., `fromquinn.com`)
2. In Netlify → "Domain settings" → "Add custom domain"
3. Follow DNS configuration instructions
4. SSL certificate auto-provisions

---

## Step 5: Share With Your Valentine! 💕

### Best Ways to Share:

1. **Text Message** (Most Impactful)
   ```
   I have something special for you 💕
   https://your-site-name.netlify.app
   ```

2. **QR Code**
   - Generate at [qr-code-generator.com](https://www.qr-code-generator.com)
   - Print and hand deliver

3. **Email**
   - Send with a sweet message

---

## Updating Your Site

### If You Need to Make Changes:

1. **Edit files locally** on your computer
2. **Commit changes:**
   - GitHub Desktop: Write message → Commit → Push
   - Command line: `git add .` → `git commit -m "message"` → `git push`
3. **Netlify auto-deploys** from GitHub (takes ~30 seconds)

---

## Common Issues & Solutions

### Problem: Site not deploying
**Solution:** Check deploy logs in Netlify → Deploys tab

### Problem: SMS not sending  
**Solution:** 
- Verify environment variables are set
- Check Twilio account balance
- Verify recipient number in Twilio console

### Problem: Button not moving
**Solution:**
- Clear browser cache
- Test in incognito mode
- Check browser console (F12) for errors

---

## Quick Reference Commands

```bash
# Check Git status
git status

# Add all changes
git add .

# Commit with message
git commit -m "Your message here"

# Push to GitHub
git push

# Pull latest changes
git pull

# View commit history
git log --oneline
```

---

## Support Resources

- **Netlify Docs:** [docs.netlify.com](https://docs.netlify.com)
- **Twilio Docs:** [twilio.com/docs](https://www.twilio.com/docs)
- **GitHub Guides:** [guides.github.com](https://guides.github.com)

---

## Checklist

- [ ] Project uploaded to GitHub (including both `first-no-image.png` and `celebration-image.png`)
- [ ] Site connected to Netlify
- [ ] Initial deploy successful
- [ ] Tested complete flow (No → Try Again → No → No → Yes)
- [ ] Button moves smoothly when evasive
- [ ] Confetti and celebration work
- [ ] Custom URL configured (optional)
- [ ] Ready to share! 💕

---

**You're all set!** 🎉 Your Valentine's website is live and ready to create some magic! ✨

**Share your unique URL and wait for that "Yes"!** 💕
