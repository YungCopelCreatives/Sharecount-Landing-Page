# ShareCount Landing Page – Real-Time Referral Tracking Setup

This guide will help you set up the real-time referral tracking system for your ShareCount landing page using Google Sheets and Google Apps Script.

---

## ✅ Final Steps Summary

1. **Set up Google Sheet with: Username, Email, IP, Referral Code, Referral Count**
2. **Add Apps Script backend and deploy as Web App**
3. **Update `scriptURL` in the code**
4. **Upload to your server or test locally with internet access**
5. **Done! All referral tracking is now real-time.**

---

## Step-by-Step Instructions

### 1. Set up Google Sheet
- Create a new Google Sheet.
- Add the following columns in the first row:
  - `Username`
  - `Email`
  - `IP`
  - `Referral Code`
  - `Referral Count`
- This sheet will store all user signups and referral data.

### 2. Add Apps Script Backend and Deploy as Web App
- In your Google Sheet, go to **Extensions > Apps Script**.
- Delete any code in the editor and paste your backend Apps Script code (handles GET/POST requests, referral logic, etc.).
- Save the script.
- Click **Deploy > New deployment**.
- Select **Web app** as the deployment type.
- Set access to **Anyone** or **Anyone with the link** (as required).
- Deploy and copy the Web App URL (this is your `scriptURL`).

#### Example Apps Script Features
- Handles new signups (adds to sheet, generates referral code).
- Tracks referrals by IP and code.
- Returns leaderboard data as JSON.

### 3. Update `scriptURL` in the Code
- In your `index.html`, find the line:
  ```js
  const scriptURL = 'https://script.google.com/macros/s/YOUR_DEPLOYED_SCRIPT_ID/exec';
  ```
- Replace the placeholder with your actual deployed Apps Script Web App URL.

### 4. Upload to Your Server or Test Locally
- Upload your updated files (including `index.html`) to your web server.
- Or, open `index.html` locally in your browser (requires internet access for Google APIs).
- Test the full flow: join waitlist, copy/share referral, and see leaderboard update in real-time.

### 5. Done! All Referral Tracking is Now Real-Time
- Users can join the waitlist, get unique referral codes, share them, and see live leaderboard updates.
- All data is managed in your Google Sheet and handled by your Apps Script backend.

---

## Tips & Best Practices
- **Security:** Do not expose sensitive data in the frontend. Use Apps Script to validate and sanitize inputs.
- **Testing:** Try the flow with multiple browsers/devices to ensure referrals are tracked correctly.
- **Sheet Management:** Periodically review your Google Sheet for duplicates or abuse.
- **Customization:** You can expand the Apps Script to send confirmation emails, handle edge cases, or add admin features.

---

For any issues or improvements, please contact the maintainer. 