# 💕 Valentine's Interactive Website - Quick Start

## What You've Got

A complete, ready-to-deploy Valentine's Day website with:
- ✅ Interactive "No" button that escalates in humor
- ✅ Celebratory "Yes" response with confetti & music
- ✅ SMS notifications to **609-608-5401**
- ✅ Beautiful romantic dark theme
- ✅ Mobile & desktop responsive
- ✅ Ready for GitHub + Netlify deployment

## Your Custom Message

When someone clicks "Yes", they'll receive this SMS:

> **"Congratulations on your decision! Our reservation is February 20th at 6:45 pm at Sage and Salt Bistro. - Love, Quinn"**

## 5-Minute Setup

### 1️⃣ Upload to GitHub (2 minutes)

**Using GitHub Desktop** (Easiest):
1. Download [GitHub Desktop](https://desktop.github.com)
2. Create new repository: `valentine-website`
3. Copy all project files to repository folder
4. Commit: "Initial Valentine's website"
5. Click "Publish repository"

**Using Command Line**:
```bash
git init
git add .
git commit -m "Initial Valentine's website"
git remote add origin https://github.com/YOUR_USERNAME/valentine-website.git
git push -u origin main
```

### 2️⃣ Deploy to Netlify (2 minutes)

1. Go to [app.netlify.com](https://app.netlify.com)
2. Click "Add new site" → "Import an existing project"
3. Select GitHub → Choose your repository
4. Click "Deploy site" (settings auto-detected!)

### 3️⃣ Set Up SMS (1 minute)

1. **Create Twilio account**: [twilio.com/try-twilio](https://www.twilio.com/try-twilio)
2. **Verify recipient number** in Twilio: `609-608-5401`
3. **Get credentials** from Twilio Console:
   - Account SID
   - Auth Token  
   - Your Twilio phone number
4. **Add to Netlify**:
   - Site settings → Environment variables
   - Add: `TWILIO_ACCOUNT_SID`, `TWILIO_AUTH_TOKEN`, `TWILIO_PHONE_NUMBER`
5. **Redeploy**: Deploys tab → Trigger deploy

### 4️⃣ Share Your Link! 💌

Send your Netlify URL via text message and wait for magic! ✨

## How It Works

1. **User sees:** "Will You Be My Valentine?"
2. **Clicks "No" (1st):** Custom "OHMYGODDDD" photo + "try again"
3. **Clicks "No" (2nd):** Warning message appears
4. **Tries "No" again:** Button moves - impossible to click!
5. **Clicks "Yes":** 🎉 Confetti! Music! SMS sent to 609-608-5401!

## File Structure
```
📁 valentine-website/
├── 📄 index.html              ← Main website
├── 🖼️ first-no-image.png      ← Custom "OHMYGODDDD" photo
├── 📄 GITHUB-DEPLOY.md        ← Full GitHub + Netlify guide
├── 📄 README.md               ← Complete documentation
├── 📄 package.json            ← Dependencies
├── 📄 netlify.toml            ← Netlify config
├── 📄 .env.example            ← Environment template
├── 📄 .gitignore              ← Git ignore rules
└── 📁 netlify/functions/  
    └── 📄 send-sms.js         ← SMS notification function
```

## Already Configured For You ✅

- ✅ Phone number set to: **+16096085401**
- ✅ Message: "Congratulations on your decision! Our reservation is February 20th at 6:45 pm at Sage and Salt Bistro. - Love, Quinn"
- ✅ Dark romantic theme (black background)
- ✅ Custom "OHMYGODDDD" photo for first "No" click
- ✅ All Netlify settings ready

## What You Need to Do

1. Upload to GitHub
2. Connect to Netlify  
3. Add Twilio credentials (for SMS)
4. Share the link!

## Need Detailed Help?

- **Full GitHub + Netlify Guide:** → See `GITHUB-DEPLOY.md`
- **Complete Documentation:** → See `README.md`
- **Twilio Setup:** → [twilio.com/try-twilio](https://www.twilio.com/try-twilio)

## Pro Tips

💡 Test the complete flow before sharing
💡 Make sure 609-608-5401 is verified in Twilio (required for trial)
💡 Send link via text message for maximum impact
💡 Change site name in Netlify for custom URL

---

**Ready to make Valentine's Day special?** 🌹

Follow the 3 steps above, then share your link and wait for the magic! ✨

**From Quinn with love** 💕
