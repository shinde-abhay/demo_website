# 🚀 DEPLOYMENT GUIDE - ASVANA STUDIO WEBSITE

Complete instructions for deploying your website to various platforms.

---

## **1. VERCEL (Recommended - Easiest)**

Vercel is ideal for static sites and offers free hosting with excellent performance.

### **Steps:**

1. **Create Vercel Account**
   - Go to vercel.com
   - Click "Sign Up"
   - Choose GitHub/GitLab/Bitbucket or email

2. **Push to GitHub First**
   ```bash
   cd asvana-website
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/yourusername/asvana-studio
   git push -u origin main
   ```

3. **Deploy on Vercel**
   - Go to vercel.com/new
   - Click "Import Git Repository"
   - Select your GitHub repo
   - Click "Deploy"
   - Done! 🎉

4. **Custom Domain (Optional)**
   - Go to Project Settings → Domains
   - Add your domain
   - Update DNS records as instructed

**Pros:**
- ✅ Free hosting
- ✅ Auto deploys on git push
- ✅ Fast CDN
- ✅ SSL included
- ✅ Easy custom domain

**Cons:**
- Requires GitHub account

---

## **2. NETLIFY**

Perfect for static websites with amazing build tools.

### **Steps:**

1. **Via GitHub (Recommended)**
   - Go to netlify.com
   - Click "New site from Git"
   - Connect GitHub
   - Select repository
   - Click "Deploy"

2. **Or Drag & Drop**
   - Go to netlify.com
   - Drag & drop your `asvana-website` folder
   - Deploy in seconds!

3. **Custom Domain**
   - Site settings → Domain management
   - Add custom domain
   - Update DNS

**Pros:**
- ✅ Super easy drag & drop
- ✅ Free hosting
- ✅ Form submissions available
- ✅ Built-in analytics

**Cons:**
- Requires account

---

## **3. GitHub Pages (Free)**

Host directly from GitHub repository.

### **Steps:**

1. **Push to GitHub**
   ```bash
   git push origin main
   ```

2. **Enable GitHub Pages**
   - Go to your repo on GitHub
   - Click "Settings"
   - Scroll to "GitHub Pages"
   - Select branch: `main`
   - Select folder: `/ (root)`
   - Click "Save"

3. **Access Your Site**
   - Visit: `https://yourusername.github.io/asvana-studio`

4. **Custom Domain**
   - Settings → Pages → Custom Domain
   - Add your domain name
   - Create CNAME file in root

**Pros:**
- ✅ Completely free
- ✅ Uses GitHub account you already have
- ✅ Simple setup

**Cons:**
- GitHub URL unless using custom domain
- Limited features

---

## **4. FIREBASE HOSTING**

Google's hosting platform with excellent performance.

### **Steps:**

1. **Install Firebase CLI**
   ```bash
   npm install -g firebase-tools
   ```

2. **Initialize Firebase**
   ```bash
   cd asvana-website
   firebase login
   firebase init hosting
   ```
   - Select your Firebase project
   - Set public directory to: `.` (current)
   - Configure as SPA: No
   - Overwrite index.html: No

3. **Deploy**
   ```bash
   firebase deploy
   ```

4. **View Live**
   - Go to Firebase Console
   - Click Hosting
   - Visit your URL

**Pros:**
- ✅ Google infrastructure
- ✅ Very fast
- ✅ Free tier available
- ✅ Analytics included

**Cons:**
- Requires more setup
- Firebase CLI needed

---

## **5. AWS S3 + CloudFront**

Professional enterprise solution.

### **Steps:**

1. **Create S3 Bucket**
   - AWS Console → S3
   - Click "Create Bucket"
   - Name: `asvana-studio-website`
   - Region: Nearest to you
   - Unblock public access
   - Click "Create"

2. **Upload Files**
   - Select bucket
   - Click "Upload"
   - Select all files from `asvana-website/`
   - Click "Upload"

3. **Enable Static Website Hosting**
   - Properties → Static website hosting
   - Enable
   - Index: `index.html`
   - Error: `index.html`
   - Save

4. **Set Bucket Policy (Make Public)**
   - Permissions → Bucket policy
   - Add:
   ```json
   {
       "Version": "2012-10-17",
       "Statement": [
           {
               "Sid": "PublicRead",
               "Effect": "Allow",
               "Principal": "*",
               "Action": "s3:GetObject",
               "Resource": "arn:aws:s3:::asvana-studio-website/*"
           }
       ]
   }
   ```

5. **Create CloudFront Distribution** (Optional but recommended)
   - CloudFront Console
   - Create distribution
   - Origin: Your S3 bucket endpoint
   - Create

**Pros:**
- ✅ Scalable
- ✅ Professional
- ✅ Global CDN

**Cons:**
- More complex setup
- May require AWS account

---

## **6. TRADITIONAL HOSTING (cPanel)**

For Bluehost, SiteGround, HostGator, etc.

### **Steps:**

1. **FTP Upload**
   - Get FTP credentials from host
   - Download FileZilla or similar
   - Connect to server
   - Navigate to `public_html`
   - Upload all files

2. **Or Using cPanel File Manager**
   - Login to cPanel
   - File Manager
   - Navigate to `public_html`
   - Upload files

3. **Point Domain**
   - cPanel → Addon Domains
   - Add your domain
   - Point to `public_html`

4. **SSL Certificate**
   - cPanel → AutoSSL
   - Install (usually automatic)

**Pros:**
- ✅ Full control
- ✅ Email hosting
- ✅ Database access

**Cons:**
- Requires paid hosting
- Manual updates
- Less scalable

---

## **7. CLOUDFLARE PAGES**

Fast, simple, and integrated with Cloudflare.

### **Steps:**

1. **Connect GitHub**
   - pages.cloudflare.com
   - "Create project"
   - Select GitHub repo
   - "Begin setup"

2. **Configure**
   - Build command: (leave empty)
   - Build output directory: (leave empty)
   - Click "Save and Deploy"

3. **Custom Domain**
   - Custom domain settings
   - Add your domain

**Pros:**
- ✅ Very fast
- ✅ Free tier
- ✅ Cloudflare integration
- ✅ Easy git integration

---

## **DOMAIN REGISTRATION**

### **Where to Buy:**
- **Namecheap** (cheap, good support)
- **GoDaddy** (popular, expensive)
- **Google Domains** (simple, integrates with services)
- **Hostinger** (affordable)

### **How to Point to Hosting:**

1. **Get Nameservers** from hosting provider
2. **Login to Domain Registrar**
3. **Update Nameservers** with registrar
4. **Wait 24-48 hours** for DNS propagation

---

## **EMAIL SETUP**

### **For Contact Form:**

1. **Gmail SMTP:**
   ```javascript
   nodemailer.createTransport({
       service: 'gmail',
       auth: {
           user: 'your-email@gmail.com',
           pass: 'your-app-password'
       }
   });
   ```

2. **Netlify Forms:**
   - No backend needed!
   - Form automatically emails you
   - Free tier: 100 submissions/month

3. **SendGrid:**
   ```bash
   npm install @sendgrid/mail
   ```
   - 100 free emails/day

---

## **PERFORMANCE CHECKLIST**

- [ ] Images optimized (compress with TinyPNG)
- [ ] CSS and JS minified
- [ ] Enable gzip compression
- [ ] Set up CDN
- [ ] Add caching headers
- [ ] Test with Google PageSpeed Insights
- [ ] Mobile responsive verified
- [ ] Cross-browser tested

---

## **SECURITY CHECKLIST**

- [ ] HTTPS/SSL enabled
- [ ] Contact form backend secure
- [ ] No sensitive data in code
- [ ] Headers configured properly
- [ ] DDoS protection enabled
- [ ] Regular backups scheduled
- [ ] Monitoring alerts set up

---

## **MONITORING & MAINTENANCE**

### **Free Tools:**

1. **Google Analytics**
   ```html
   <!-- Add to <head> in index.html -->
   <script async src="https://www.googletagmanager.com/gtag/js?id=GA_ID"></script>
   <script>
       window.dataLayer = window.dataLayer || [];
       function gtag(){dataLayer.push(arguments);}
       gtag('js', new Date());
       gtag('config', 'GA_ID');
   </script>
   ```

2. **Uptime Monitoring**
   - UptimeRobot (free)
   - Pingdom (free tier)

3. **Performance Testing**
   - Google PageSpeed Insights
   - Lighthouse
   - GTmetrix

---

## **DEPLOYMENT COMPARISON TABLE**

| Platform | Cost | Setup | Ease | Features |
|----------|------|-------|------|----------|
| **Vercel** | Free | ⭐⭐ | ⭐⭐⭐ | Excellent |
| **Netlify** | Free | ⭐⭐ | ⭐⭐⭐ | Great |
| **GitHub Pages** | Free | ⭐⭐⭐ | ⭐⭐ | Basic |
| **Firebase** | Free tier | ⭐⭐ | ⭐⭐ | Good |
| **AWS** | Free tier | ⭐ | ⭐ | Excellent |
| **Traditional** | $5-15/mo | ⭐⭐ | ⭐⭐ | Full control |

---

## **RECOMMENDED PATH**

### **For Beginners:**
1. Use **Netlify** (easiest)
2. Add GitHub repo
3. Deploy with one click
4. Get free SSL
5. Add custom domain

### **For Best Performance:**
1. Use **Vercel**
2. Link GitHub
3. Auto deploys on push
4. Global CDN
5. Add custom domain

### **For Complete Control:**
1. Get traditional hosting (SiteGround)
2. Upload via FTP
3. Use own email
4. Full customization

---

## **POST-DEPLOYMENT TASKS**

- [ ] Test all links work
- [ ] Verify responsiveness on mobile
- [ ] Check contact form sends emails
- [ ] Add Google Analytics
- [ ] Submit to Google Search Console
- [ ] Add to Google Business Profile
- [ ] Set up email forwarding
- [ ] Create sitemap.xml
- [ ] Add robots.txt
- [ ] Monitor performance

---

## **TROUBLESHOOTING**

### **404 Errors on Pages**
- Ensure all links are relative (e.g., `#services` not `/services`)
- Check file paths are correct

### **Images Not Loading**
- Verify images are in uploaded folder
- Check file names match exactly
- Use relative paths

### **Contact Form Not Working**
- Configure backend endpoint
- Check browser console for errors
- Verify email service is connected

### **DNS Not Working**
- Wait 24-48 hours for propagation
- Clear browser DNS cache
- Check nameserver is updated

---

**Choose your platform and deploy! Your website will be live in minutes! 🎉**
