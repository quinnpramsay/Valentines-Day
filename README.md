# 💕 Valentine's Day Interactive Website

A minimal, clean interactive Valentine's Day website that playfully nudges users toward saying "Yes." Features a simple black background with pink text and is pre-configured for deployment from GitHub to Netlify with SMS notifications.

## ✨ Features

- **Interactive "No" Escalation System**
  - 1st "No": Shows custom image, heading changes to "No is not an option.", "Try Again" button appears
  - Click "Try Again": Returns to question "Will you be my Valentine?" with normal buttons
  - 2nd "No": Message "I said no is not an option." appears briefly, button still clickable
  - 3rd "No": Button starts smoothly moving away (impossible to click)
  - Subsequent attempts: "No" button continues moving (stays on screen)

- **Celebratory "Yes" Response**
  - Confetti animation
  - Custom message and photo
  - Smooth celebration display

- **Minimal, Clean Design**
  - Solid black background
  - Simple pink text (no emojis)
  - Clean Inter font (no decorative fonts)
  - No extra animations or effects
  - Small "No" button, normal "Yes" button

## 📱 Pre-Configured Settings

This website is already set up with:
- **Celebration message:** "Hell fucking yea lets go, see you then!"
- **Minimal clean design** with black background and pink text
- **Smooth button evasion** with natural movement
- **Custom photos** for reactions and celebration

## 🚀 Quick Start

### Prerequisites

- A GitHub account (free)
- A Netlify account (free tier works perfectly)

### Simple 2-Step Deployment

1. **Upload to GitHub**
   - Create a new repository
   - Upload all project files
   - See `GITHUB-DEPLOY.md` for detailed instructions

2. **Deploy to Netlify**
   - Connect your GitHub repository to Netlify
   - Netlify auto-detects settings from `netlify.toml`
   - Site deploys automatically

**📖 For complete step-by-step instructions, see `GITHUB-DEPLOY.md`**

### 1. Customize Your Content (Optional)

The site is already configured with Quinn's settings, but you can customize if needed.

Edit `index.html` and modify the `CONFIG` object (around line 225):

```javascript
const CONFIG = {
    // Currently configured:
    firstNoImage: 'first-no-image.png', // Custom "OHMYGODDDD" photo
    celebrationImage: 'celebration-image.png', // Custom celebration photo
    
    // Pre-configured messages
    celebrationMessage: "Hell fucking yea lets go, see you then!",
    firstNoMessage: "Noooooo, Wrong, try again",
    secondNoMessage: "Choose again wisely or there will be issues",
    confirmationMessage: "Congratulations on your decision! Our reservation is February 20th at 6:45 pm at Sage and Salt Bistro. - Love, Quinn",
    
    // Pre-configured recipient
    phoneNumber: '+16096085401', // 609-608-5401
    
    netlifyFunctionUrl: '/.netlify/functions/send-sms'
};
```

**Note:** The project includes two custom image files:
- `first-no-image.png` - Displays when "No" is first clicked
- `celebration-image.png` - Displays when "Yes" is clicked

Make sure to include both files when uploading to GitHub!

### 2. Deploy via GitHub + Netlify

See `GITHUB-DEPLOY.md` for complete instructions, or quick version:

**Upload to GitHub:**
```bash
git init
git add .
git commit -m "Initial Valentine's website"
git remote add origin https://github.com/YOUR_USERNAME/valentine-website.git
git push -u origin main
```

**Deploy to Netlify:**
1. Go to [app.netlify.com](https://app.netlify.com)
2. Click "Add new site" → "Import an existing project"  
3. Choose GitHub → Select your repository
4. Click "Deploy site"

### 3. Set Up Twilio (for SMS notifications)

1. **Create a Twilio account**
   - Sign up at [twilio.com/try-twilio](https://www.twilio.com/try-twilio)
   - Get a free trial phone number

2. **Verify the recipient number**
   - In Twilio Console → "Phone Numbers" → "Verified Caller IDs"
   - Click "Add a new number"
   - Enter: **+16096085401** (or 609-608-5401)
   - Complete verification process
   - **This step is REQUIRED for trial accounts**

3. **Get your credentials**
   - Account SID: Found in Twilio Console dashboard
   - Auth Token: Found in Twilio Console (click to reveal - keep secret!)
   - Phone Number: Your Twilio phone number (the one they give you)

4. **Add to Netlify environment variables**
   - In Netlify Dashboard → Site settings → Environment variables
   - Add these three variables:
     ```
     TWILIO_ACCOUNT_SID = your_twilio_account_sid
     TWILIO_AUTH_TOKEN = your_twilio_auth_token  
     TWILIO_PHONE_NUMBER = your_twilio_phone_number (e.g., +12125551234)
     ```

5. **Redeploy**
   - Go to Deploys → Trigger deploy → Deploy site
   - SMS functionality is now active!

## 🎨 Customization Guide

### Changing Images

Replace URLs in the `CONFIG` object with your own:

- **firstNoImage**: Image shown on first "No" click (currently using custom uploaded photo)
- **celebrationImage**: Celebration GIF or image shown when "Yes" is clicked

**Where to find media:**
- [Giphy](https://giphy.com) - Free GIFs
- [Tenor](https://tenor.com) - Free GIFs
- [Pexels](https://pexels.com) - Free images
- Upload your own to [Imgur](https://imgur.com) or [Cloudinary](https://cloudinary.com)

### Changing the Celebration Music

Replace the audio source in `index.html` (around line 142):

```html
<audio id="celebrationAudio" preload="auto">
    <source src="YOUR_AUDIO_URL.mp3" type="audio/mpeg">
</audio>
```

**Recommended:** Use "Celebration" by Kool & The Gang or any upbeat song.

**Note:** Due to browser autoplay policies, audio may require user interaction to play.

### Changing Colors

The site uses a dark romantic theme. Modify CSS variables in `index.html` (around line 17):

```css
:root {
    --primary-pink: #FF6B9D;      /* Main pink accent */
    --secondary-pink: #FFC1E3;    /* Lighter pink */
    --accent-red: #FF4757;        /* Red highlights */
    --soft-cream: #FFF5F7;        /* Light text */
    --text-dark: #2C0E37;         /* Dark text */
    --dark-bg: #0a0a0a;           /* Main background */
    --dark-secondary: #1a1a1a;    /* Secondary background */
}
```

**Background gradient** (around line 24):
```css
background: linear-gradient(135deg, #000000 0%, #1a0a0f 50%, #0a0a0a 100%);
```

### Changing Fonts

Replace Google Fonts link in `<head>` section:

```html
<link href="https://fonts.googleapis.com/css2?family=YOUR_FONT&display=swap" rel="stylesheet">
```

Then update CSS:
```css
h1 {
    font-family: 'YOUR_FONT', cursive;
}
```

## 📱 Testing Locally

1. **Install dependencies**
   ```bash
   npm install
   ```

2. **Create `.env` file** in project root:
   ```
   TWILIO_ACCOUNT_SID=your_account_sid
   TWILIO_AUTH_TOKEN=your_auth_token
   TWILIO_PHONE_NUMBER=your_phone_number
   ```

3. **Run with Netlify Dev**
   ```bash
   netlify dev
   ```

4. **Open in browser**
   - Go to `http://localhost:8888`
   - Test all functionality

## 🔧 Troubleshooting

### SMS not sending

1. Check Netlify function logs: Netlify Dashboard → Functions → View logs
2. Verify environment variables are set correctly
3. Ensure Twilio credentials are valid
4. Check Twilio account balance (trial accounts need credits)
5. Verify phone number format: `+1234567890` (include country code)

### Audio not playing

- Modern browsers block autoplay of audio
- User must interact with page first (click anywhere)
- Solution is already implemented: audio will play after first user click

### Button not moving (evasive mode)

- Evasive mode activates after 3rd "No" click
- Check browser console for JavaScript errors
- Ensure viewport is large enough for button movement

### Images/Videos not loading

- Verify URLs are accessible (open in new tab)
- Some sites block hotlinking - use Imgur or Cloudinary instead
- Check browser console for CORS errors

## 📋 File Structure

```
valentine-website/
├── index.html              # Main website file
├── first-no-image.png      # Custom image shown on first "No" click
├── celebration-image.png   # Custom image shown on "Yes" celebration
├── netlify.toml           # Netlify configuration
├── package.json           # Dependencies
├── README.md             # This file
├── QUICKSTART.md         # Quick start guide
├── GITHUB-DEPLOY.md      # GitHub deployment instructions
├── .env.example          # Environment variables template
├── .gitignore            # Git ignore rules
└── netlify/
    └── functions/
        └── send-sms.js   # SMS notification function
```

## 🎯 Success Checklist

- [ ] Files uploaded to GitHub (including both image files)
- [ ] Site connected to Netlify and deployed
- [ ] Website loads with clean black background and pink text
- [ ] First "No" shows custom image, heading changes, "Try Again" button visible
- [ ] Click "Try Again" returns to "Will you be my Valentine?" with normal buttons
- [ ] Second "No" shows "I said no is not an option." message briefly
- [ ] Third "No" makes button start moving smoothly (stays on screen)
- [ ] Button continues moving with smooth, natural animations
- [ ] Clicking "Yes" triggers:
  - [ ] Confetti animation
  - [ ] Custom message and photo display

## 🔒 Security Notes

- Never commit `.env` file to Git (already in `.gitignore`)
- Keep Twilio credentials secret
- Use environment variables for all sensitive data
- Netlify automatically secures function endpoints

## 💡 Tips

- **Test thoroughly** before sending to your Valentine
- **Backup plan**: If SMS fails, you'll still see the celebration
- **Mobile-friendly**: Site works great on phones and tablets
- **Share the link**: Send via text, email, or social media
- **Custom domain**: Netlify allows custom domains (e.g., `bemyvalentine.com`)

## 📄 License

MIT License - Feel free to customize and share!

## 💌 Support

If you encounter issues:
1. Check browser console for errors (F12 → Console)
2. Review Netlify function logs
3. Verify all environment variables
4. Test with Netlify Dev locally

---

Made with 💕 for Valentine's Day

**Happy Valentine's Day!** 🌹
