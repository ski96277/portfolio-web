# 🔥 Firebase Analytics Setup Guide

## 📋 **Setup Steps**

### 1. **Create Firebase Project**
1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Click "Create a project" or "Add project"
3. Enter project name: `portfolio-analytics` (or your preferred name)
4. Enable Google Analytics (recommended)
5. Choose your Analytics account or create a new one
6. Click "Create project"

### 2. **Add Web App to Firebase**
1. In your Firebase project dashboard, click the web icon `</>`
2. Register your app with a nickname: `portfolio-website`
3. **Copy the Firebase configuration object** (you'll need this!)

### 3. **Enable Analytics**
1. In Firebase Console, go to **Analytics** → **Events**
2. Make sure Analytics is enabled for your project
3. Go to **Project Settings** → **General** → **Your apps**
4. Find your web app and copy the `measurementId`

### 4. **Update Configuration**
Replace the placeholder values in `index.html` (around line 1075):

```javascript
const firebaseConfig = {
    apiKey: "your-actual-api-key",
    authDomain: "your-project.firebaseapp.com",
    projectId: "your-actual-project-id",
    storageBucket: "your-project.appspot.com",
    messagingSenderId: "123456789",
    appId: "your-actual-app-id",
    measurementId: "G-XXXXXXXXXX"  // This is your Analytics ID
};
```

### 5. **Test Analytics**
1. Open your website: `http://localhost:8000`
2. Accept the privacy notice
3. Navigate around your portfolio
4. Check Firebase Console → **Analytics** → **Events** for real-time data

## 📊 **What We Track**

### **Automatic Tracking:**
- 📍 **Location**: Country/region (with user consent)
- ⏱️ **Time Spent**: Session duration and page time
- 📊 **Page Views**: Which pages are visited
- 📱 **Device Info**: Browser, OS, screen size
- 🔗 **Link Clicks**: Internal and external links

### **Custom Events:**
- `section_view`: When users view portfolio sections
- `navigation_click`: Internal navigation clicks
- `menu_item_click`: **Detailed menu click tracking with counters**
- `menu_statistics_summary`: **Periodic menu usage statistics**
- `external_link_click`: Social media and external links
- `theme_toggle`: Dark/light theme switches
- `mobile_menu_toggle`: Mobile menu usage
- `scroll`: Scroll depth (25%, 50%, 75%, 90%)
- `session_duration`: Time spent on website

### **📊 Menu Click Analytics:**
- **Individual Click Counts**: How many times each menu item is clicked
- **Total Menu Clicks**: Overall navigation activity
- **Most Clicked Item**: Which section gets the most attention
- **Click Timestamps**: When each click occurs
- **Device Information**: Screen resolution, viewport size
- **Periodic Summaries**: Statistics logged every 5 minutes
- **Session End Summary**: Final menu usage when leaving

### **Privacy Compliant:**
- ✅ **User Consent**: Privacy notice before tracking
- ✅ **No Personal Data**: Only anonymous analytics
- ✅ **Location Optional**: Only with user permission
- ✅ **GDPR Compliant**: Clear consent mechanism

## 🎯 **Analytics Dashboard**

### **Key Metrics to Monitor:**
1. **User Engagement**
   - Average session duration
   - Pages per session
   - Bounce rate

2. **Content Performance**
   - Most viewed sections
   - Scroll depth analysis
   - External link clicks

3. **User Behavior**
   - Theme preferences
   - Mobile vs desktop usage
   - Navigation patterns

4. **Geographic Data**
   - Visitor locations
   - Regional engagement

## 🔧 **Customization**

### **Add More Events:**
```javascript
// Track custom interactions
window.portfolioAnalytics.logEvent('custom_event', {
    event_category: 'engagement',
    event_label: 'specific_action'
});
```

### **User Properties:**
```javascript
// Set user properties
window.portfolioAnalytics.setUserProperties({
    user_type: 'visitor',
    source: 'direct'
});
```

## 📱 **Mobile Analytics**

The analytics work seamlessly on mobile devices and track:
- Touch interactions
- Mobile menu usage
- Responsive behavior
- Mobile-specific events

## 🛡️ **Privacy & Compliance**

- **Consent Required**: Users must accept before tracking
- **Anonymous Data**: No personal information collected
- **Local Storage**: Consent preference saved locally
- **Opt-out Available**: Users can decline analytics
- **Transparent**: Clear explanation of what's tracked

## 🚀 **Deployment**

### **Custom Domain Setup (imransk.me):**
Your portfolio is configured for your custom domain `imransk.me` hosted on GitHub Pages.

**Firebase Configuration:**
- ✅ **Project ID**: `imran-sportfolio`
- ✅ **Analytics ID**: `G-L4481WHEKK`
- ✅ **Custom Domain**: `imransk.me`
- ✅ **GitHub Pages**: Ready for deployment

**Domain Verification:**
1. In Firebase Console → **Project Settings** → **General**
2. Add your domain `imransk.me` to authorized domains
3. Verify domain ownership if required
4. Analytics will work on both `localhost:8000` (development) and `imransk.me` (production)

**GitHub Pages Deployment:**
1. Push your code to GitHub repository
2. Enable GitHub Pages in repository settings
3. Set custom domain to `imransk.me`
4. Analytics will automatically work on your live domain

## 📈 **Reports & Insights**

Access your analytics data in:
- **Firebase Console** → **Analytics** → **Events**
- **Google Analytics** (if connected)
- **Real-time reports** for live monitoring
- **Custom dashboards** for specific metrics

---

**🎉 Your portfolio now has professional analytics tracking!**

Monitor visitor behavior, optimize user experience, and make data-driven decisions about your portfolio content and design.
