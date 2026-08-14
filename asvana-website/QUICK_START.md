# 🚀 QUICK START GUIDE

## **Fastest Way to Run (Choose One)**

### ⚡ **Option 1: Python (Simplest)**
```bash
cd asvana-website
python -m http.server 8000
```
Then open: **http://localhost:8000**

---

### ⚡ **Option 2: Live Server Extension (VS Code)**
1. Install "Live Server" extension in VS Code
2. Right-click on `index.html`
3. Click "Open with Live Server"
4. Done! ✅ Browser opens automatically

---

### ⚡ **Option 3: http-server (Node.js)**
```bash
npm install -g http-server
cd asvana-website
http-server
```
Then open: **http://localhost:8080**

---

## 📁 **File Structure You Need**

```
asvana-website/
├── index.html          ✅ MAIN FILE
├── assets/
│   ├── css/
│   │   ├── styles.css
│   │   └── responsive.css
│   ├── js/
│   │   └── script.js
│   └── images/         ⬅️ Add your images here
├── README.md
└── QUICK_START.md      ⬅️ This file
```

---

## 🖼️ **Add Your Images**

Create folder: `assets/images/`

Add these files:
- `hero-landscape.jpg` (1200x600px)
- `portfolio-1.jpg` to `portfolio-5.jpg` (500x625px each)

---

## 🎨 **Quick Customizations**

### **Change Business Name:**
Open `index.html`, find:
```html
<div class="logo-main">ASVANA</div>
<div class="logo-sub">STUDIO</div>
```

### **Change Phone Number:**
Open `index.html`, find:
```html
<p>+91 8485021449</p>
```

### **Change Email:**
Open `index.html`, find:
```html
<p>asvanastudio@gmail.com</p>
```

### **Change Colors:**
Open `assets/css/styles.css`, find:
```css
:root {
    --primary: #2d5f4f;        /* Change this */
    --accent: #d4a574;         /* Or this */
    --cream: #f5f1e8;          /* Or this */
}
```

---

## ✅ **Verification Checklist**

- [ ] All 3 CSS files are in `assets/css/`
- [ ] JavaScript file is in `assets/js/`
- [ ] Images are in `assets/images/`
- [ ] Running via local server (not direct file)
- [ ] Browser console shows no errors (F12)
- [ ] Responsive - mobile view works (F12 → Toggle device)

---

## 🔧 **Common Issues & Fixes**

| Problem | Solution |
|---------|----------|
| Images not showing | Check `assets/images/` folder exists |
| Styles look broken | Hard refresh: `Ctrl+F5` |
| Script errors | Open F12 console, check errors |
| Port 8000 taken | Use `python -m http.server 8001` |
| Can't run Python | Install Python or use Node.js option |

---

## 📱 **Test on Mobile**

1. Get your computer IP: `ipconfig` (Windows) or `ifconfig` (Mac/Linux)
2. On phone, visit: `http://YOUR_IP:8000`
3. Test all pages and buttons

---

## 🚀 **Deploy When Ready**

### **Free Options:**
- **Vercel** (easiest - just upload folder)
- **Netlify** (drag & drop)
- **GitHub Pages** (push to GitHub)

---

## 📞 **Need Help?**

1. Check **README.md** for detailed troubleshooting
2. Open browser console (F12) for error messages
3. Verify all files are in correct folders
4. Try a different browser

---

**That's it! You're ready to go! 🎉**

Open http://localhost:8000 and enjoy your website!
