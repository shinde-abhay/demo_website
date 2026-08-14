# ASVANA STUDIO - Website

A modern, responsive website for ASVANA STUDIO - Where Family and Nature Shape Design.

## 📁 Project Structure

```
asvana-website/
├── index.html              # Main homepage
├── assets/
│   ├── css/
│   │   ├── styles.css      # Main stylesheet
│   │   └── responsive.css  # Mobile/tablet responsive styles
│   ├── js/
│   │   └── script.js       # JavaScript interactivity
│   ├── images/             # Image assets folder
│   │   ├── hero-landscape.jpg
│   │   ├── portfolio-1.jpg through portfolio-5.jpg
│   │   └── (add your images here)
├── README.md               # This file
└── package.json            # Optional Node.js config
```

## 🚀 How to Run the Website

### **Method 1: Python (Recommended - Easiest)**

#### For Python 3.x:
```bash
cd asvana-website
python -m http.server 8000
```

Then open your browser and go to:
```
http://localhost:8000
```

#### For Python 2.x:
```bash
cd asvana-website
python -m SimpleHTTPServer 8000
```

---

### **Method 2: Node.js / npm**

#### Option A: Using http-server (Recommended)

1. **Install http-server globally:**
```bash
npm install -g http-server
```

2. **Run the server:**
```bash
cd asvana-website
http-server
```

3. **Open in browser:**
```
http://localhost:8080
```

#### Option B: Using Live Server (npm)

1. **Install live-server:**
```bash
npm install -g live-server
```

2. **Run the server:**
```bash
cd asvana-website
live-server
```

3. **Browser will open automatically** with live reload enabled

---

### **Method 3: VS Code Live Server Extension**

1. **Install the extension:**
   - Open VS Code
   - Go to Extensions (Ctrl+Shift+X or Cmd+Shift+X)
   - Search for "Live Server"
   - Install by Ritwick Dey

2. **Run the server:**
   - Right-click on `index.html`
   - Click "Open with Live Server"
   - Website opens automatically at `http://127.0.0.1:5500`

---

### **Method 4: Using Node.js Express (For Advanced Users)**

1. **Create a simple server:**

Create `server.js` in the root directory:
```javascript
const express = require('express');
const path = require('path');
const app = express();

app.use(express.static(path.join(__dirname)));

app.get('/', (req, res) => {
    res.sendFile(path.join(__dirname, 'index.html'));
});

const PORT = 3000;
app.listen(PORT, () => {
    console.log(`Server running at http://localhost:${PORT}`);
});
```

2. **Install Express:**
```bash
npm install express
```

3. **Run the server:**
```bash
node server.js
```

---

### **Method 5: Direct File Opening (Not Recommended)**

Simply open `index.html` in your browser:
- Windows: Double-click the file or right-click → Open with → Browser
- Mac: Double-click the file
- Linux: Right-click → Open with → Browser

⚠️ **Note:** Some features may not work properly without a local server.

---

## 📋 System Requirements

- **Any modern browser** (Chrome, Firefox, Safari, Edge)
- **Python 3.x** OR **Node.js** (for running server)
- **No internet required** (except for Google Fonts CDN)

---

## 🖼️ Adding Images

Place your images in the `assets/images/` folder:

```
assets/images/
├── hero-landscape.jpg
├── portfolio-1.jpg
├── portfolio-2.jpg
├── portfolio-3.jpg
├── portfolio-4.jpg
└── portfolio-5.jpg
```

**Image Specifications:**
- **Hero Image:** 1200x600px (or larger, will be auto-fitted)
- **Portfolio Items:** Square format (500x625px recommended for 4:5 ratio)
- **Format:** JPG, PNG, WebP

---

## 🎨 Customization Guide

### **Change Brand Colors:**
Edit `assets/css/styles.css` - Find the `:root` section:

```css
:root {
    --primary: #2d5f4f;          /* Main green */
    --accent: #d4a574;           /* Gold/Brown */
    --cream: #f5f1e8;            /* Cream background */
}
```

### **Update Contact Information:**
Edit `index.html` - Find the Contact Section:

```html
<div class="info-item">
    <i class="fas fa-phone"></i>
    <div>
        <h4>CONTACT</h4>
        <p>+91 8485021449</p>
    </div>
</div>
```

### **Change Text Content:**
All content is in `index.html`. Find the relevant section and edit directly.

### **Update Logo Text:**
In the navbar section of `index.html`:

```html
<div class="logo-text">
    <div class="logo-main">ASVANA</div>
    <div class="logo-sub">STUDIO</div>
</div>
```

---

## 📱 Responsive Features

The website is fully responsive across:
- ✅ Desktop (1024px+)
- ✅ Tablet (768px - 1024px)
- ✅ Mobile Landscape (568px - 767px)
- ✅ Mobile Portrait (< 568px)
- ✅ Small Mobile (< 400px)

Test on mobile by:
1. Opening the website in browser
2. Pressing F12 (or Cmd+Option+I on Mac)
3. Clicking the device toggle icon
4. Selecting different devices to preview

---

## ⚙️ Features

- ✨ Modern, elegant design
- 📱 Fully responsive layout
- 🎨 Custom color scheme inspired by nature
- 🔄 Smooth scroll animations
- 📧 Contact form ready for backend integration
- ♿ Accessibility features included
- 🚀 SEO-friendly structure
- 🎯 Mobile-first approach
- 💫 Hover effects and transitions
- 🌙 Dark mode support

---

## 📧 Contact Form Integration

To make the contact form functional, add your backend endpoint:

In `assets/js/script.js`, find the contact form handler and replace:

```javascript
try {
    // Replace this line with your actual backend endpoint
    const response = await fetch('https://your-backend.com/send-email', {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json',
        },
        body: JSON.stringify(formData)
    });
    
    if (response.ok) {
        showNotification('Message sent successfully!', 'success');
        contactForm.reset();
    }
} catch (error) {
    showNotification('Error sending message.', 'error');
}
```

---

## 🔗 External Resources Used

- **Google Fonts:** Playfair Display & Lato
- **Font Awesome:** Icons (via CDN)
- **No dependencies** - Pure HTML, CSS, JavaScript

---

## 🐛 Troubleshooting

### **Issue: Site shows "Cannot GET /" **
**Solution:** Make sure you're running a local server, not opening the file directly.

### **Issue: Images not loading**
**Solution:** 
1. Verify images are in `assets/images/` folder
2. Check file names match exactly (case-sensitive on Linux)
3. Use correct image formats (JPG, PNG, WebP)

### **Issue: Styles not applying**
**Solution:**
1. Hard refresh the page (Ctrl+F5 or Cmd+Shift+R)
2. Clear browser cache
3. Check that CSS files are in `assets/css/` folder

### **Issue: JavaScript not working**
**Solution:**
1. Check browser console (F12) for errors
2. Verify script.js is in `assets/js/` folder
3. Ensure you're running via a local server

### **Issue: Port already in use**
**Solution:** Use a different port:

**Python:**
```bash
python -m http.server 8001
```

**http-server:**
```bash
http-server -p 8001
```

---

## 📚 Browser Compatibility

| Browser | Support |
|---------|---------|
| Chrome | ✅ Full |
| Firefox | ✅ Full |
| Safari | ✅ Full |
| Edge | ✅ Full |
| IE 11 | ⚠️ Limited |

---

## 📈 Performance Tips

1. **Optimize Images:** Compress JPG/PNG files using:
   - TinyPNG (tinypng.com)
   - ImageOptim (on Mac)
   - FileOptimizer (on Windows)

2. **Enable Caching:** Add to your server config
3. **Minify CSS/JS:** Use tools like:
   - CSSNano
   - Terser
   - UglifyJS

4. **Use CDN:** For faster font loading

---

## 🚀 Deployment Options

### **Free Hosting:**
1. **Vercel** (recommended)
   - Push to GitHub
   - Connect to Vercel
   - Auto-deploy on push

2. **Netlify**
   - Drag & drop folder
   - Or connect GitHub

3. **GitHub Pages**
   - Push to GitHub
   - Enable GitHub Pages
   - Free hosting with custom domain support

4. **Firebase Hosting**
   - Firebase CLI
   - Deploy with one command

### **Paid Hosting:**
- Bluehost
- SiteGround
- HostGator
- AWS S3 + CloudFront

---

## 📝 License

This website template is created for ASVANA STUDIO. Feel free to customize and use.

---

## 💡 Tips for Best Results

1. **Test on real devices** before deployment
2. **Use Google Lighthouse** to check performance
3. **Validate HTML** at validator.w3.org
4. **Test accessibility** with WAVE tool
5. **Get SSL certificate** when deploying to production
6. **Set up email backend** for contact form
7. **Add Google Analytics** for tracking
8. **Update content regularly** to keep site fresh

---

## 🤝 Support

For questions or issues:
1. Check the troubleshooting section above
2. Review browser console (F12)
3. Verify file structure matches the project layout

---

**Happy designing with ASVANA STUDIO! 🍃**
