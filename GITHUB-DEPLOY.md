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

### B. Set Up SMS Notifications (Twilio)

1. **Create Twilio Account**
   - Go to [twilio.com/try-twilio](https://www.twilio.com/try-twilio)
   - Sign up for free trial
   - Verify your phone number

2. **Get Twilio Credentials**
   - In [Twilio Console](https://console.twilio.com):
     - Copy **Account SID**
     - Copy **Auth Token** (click to reveal)
   
3. **Get Phone Number**
   - Go to "Phone Numbers" in Twilio Console
   - Click "Get a trial number"
   - Accept the number provided

4. **Verify Recipient Number (Trial Accounts)**
   - Go to "Phone Numbers" → "Verified Caller IDs"
   - Click "Add a new number"
   - Enter: `+16096085401`
   - Follow verification steps

5. **Add Environment Variables in Netlify**
   - In Netlify Dashboard → Your site
   - Go to "Site settings" → "Environment variables"
   - Click "Add a variable" for each:

   | Variable Name | Value |
   |--------------|-------|
   | `TWILIO_ACCOUNT_SID` | Your Account SID from Twilio |
   | `TWILIO_AUTH_TOKEN` | Your Auth Token from Twilio |
   | `TWILIO_PHONE_NUMBER` | Your Twilio number (e.g., +12125551234) |

6. **Redeploy Site**
   - Go to "Deploys" tab
   - Click "Trigger deploy" → "Deploy site"
   - Wait for deploy to complete

---

## Step 3: Test Your Site

### Test the Flow

1. **Visit your site** at the Netlify URL
2. **Click "No"** - Image appears, you're forced to wait 10 seconds, then "Sorry, no is not an option." message appears
3. **Click "No" again** - "I said no is not an option." message, then button starts smoothly moving away
4. **Try "No" again** - Button continues moving (impossible to click)
5. **Click "Yes"** - Should see:
   - ✨ Confetti animation
   - 🎵 Music plays
   - 💕 Custom message: "Hell fucking yea lets go, see you then!"
   - 🖼️ Custom celebration photo
   - 📱 **SMS sent to +16096085401**

### Check SMS Delivery

- SMS should arrive within seconds
- Message: "Congratulations on your decision! Our reservation is February 20th at 6:45 pm at Sage and Salt Bistro. - Love, Quinn"

### Troubleshooting

If SMS doesn't arrive:

1. **Check Netlify Function Logs**
   - Netlify Dashboard → "Functions" tab
   - Click "send-sms"
   - View invocation logs

2. **Verify Environment Variables**
   - Go to Site settings → Environment variables
   - Make sure all three Twilio variables are set

3. **Check Twilio Dashboard**
   - Go to Twilio Console → Monitor → Logs
   - See if message was sent/failed

4. **Trial Account Limitations**
   - Trial accounts can ONLY send to verified numbers
   - Make sure +16096085401 is verified in Twilio

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

### Problem: Audio not playing
**Solution:**
- Browsers block autoplay
- Audio will play after first user interaction
- This is expected behavior

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
- [ ] Twilio account created
- [ ] Recipient number verified in Twilio
- [ ] Environment variables added in Netlify
- [ ] Site redeployed after adding variables
- [ ] Tested complete flow (No → No → Yes)
- [ ] SMS received successfully
- [ ] Custom URL configured (optional)
- [ ] Ready to share! 💕

---

**You're all set!** 🎉 Your Valentine's website is live and ready to create some magic! ✨

**Share your unique URL and wait for that "Yes"!** 💕
