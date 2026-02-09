# 💕 Valentine's Day Interactive Website

A playful, interactive Valentine's Day website that humorously nudges users toward saying "Yes" while escalating responses to "No." Features a romantic dark theme and is pre-configured for deployment from GitHub to Netlify with SMS notifications.

## ✨ Features

- **Interactive "No" Escalation System**
  - 1st "No": Shows custom image with message
  - 2nd "No": Warning message appears
  - Subsequent attempts: "No" button becomes impossible to click (moves away on hover)

- **Celebratory "Yes" Response**
  - Confetti animation
  - Celebration music (configurable)
  - Custom congratulations message
  - SMS notification sent to **609-608-5401**

- **Beautiful Dark Theme Design**
  - Romantic black gradient background
  - Glowing pink accents and borders
  - Floating heart animations
  - Responsive mobile and desktop layout
  - Custom fonts (Pacifico + Quicksand)
  - Smooth animations and transitions

## 📱 Pre-Configured Settings

This website is already set up with:
- **Phone Number:** +16096085401 (609-608-5401)
- **SMS Message:** "Congratulations on your decision! Our reservation is February 20th at 6:45 pm at Sage and Salt Bistro. - Love, Quinn"
- **Dark romantic theme** with black background and pink accents

## 🚀 Quick Start

### Prerequisites

- A GitHub account (free)
- A Netlify account (free tier works perfectly)
- A Twilio account for SMS notifications (free trial available)

### Simple 3-Step Deployment

1. **Upload to GitHub**
   - Create a new repository
   - Upload all project files
   - See `GITHUB-DEPLOY.md` for detailed instructions

2. **Deploy to Netlify**
   - Connect your GitHub repository to Netlify
   - Netlify auto-detects settings from `netlify.toml`
   - Site deploys automatically

3. **Configure SMS (Twilio)**
   - Sign up at [twilio.com](https://www.twilio.com)
   - Verify the recipient number: **609-608-5401**
   - Add credentials as environment variables in Netlify

**📖 For complete step-by-step instructions, see `GITHUB-DEPLOY.md`**

### 1. Customize Your Content (Optional)

The site is already configured with Quinn's settings, but you can customize if needed.

Edit `index.html` and modify the `CONFIG` object (around line 225):

```javascript
const CONFIG = {
    // Currently configured:
    firstNoImage: 'first-no-image.png', // Custom uploaded photo
    celebrationImage: 'https://media.giphy.com/media/g9582DNuQppxC/giphy.gif',
    
    // Pre-configured messages
    celebrationMessage: "We're going to have the best Valentine's Day ever! 💕",
    firstNoMessage: "Noooooo, Wrong, try again",
    secondNoMessage: "Choose again wisely or there will be issues",
    confirmationMessage: "Congratulations on your decision! Our reservation is February 20th at 6:45 pm at Sage and Salt Bistro. - Love, Quinn",
    
    // Pre-configured recipient
    phoneNumber: '+16096085401', // 609-608-5401
    
    netlifyFunctionUrl: '/.netlify/functions/send-sms'
};
```

**Note:** The project includes a custom image file `first-no-image.png` that displays when "No" is first clicked. Make sure to include this file when uploading to GitHub!

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

- [ ] Files uploaded to GitHub (including `first-no-image.png`)
- [ ] Site connected to Netlify and deployed
- [ ] Twilio account created
- [ ] Recipient number **609-608-5401** verified in Twilio
- [ ] Environment variables added in Netlify (all 3)
- [ ] Site redeployed after adding variables
- [ ] Website loads quickly on first visit
- [ ] First "No" shows custom image and message
- [ ] Second "No" shows warning message
- [ ] After 2nd "No", button becomes impossible to click
- [ ] Clicking "Yes" triggers:
  - [ ] Confetti animation
  - [ ] Celebration music
  - [ ] Custom message displays
  - [ ] SMS sent to **609-608-5401** with reservation details

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
