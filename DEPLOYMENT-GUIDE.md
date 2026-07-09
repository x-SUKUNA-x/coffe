# Deployment Guide for Ooty Coffee Estates

This guide will help you deploy the website to various hosting platforms.

## 🚀 Quick Start

The website is built with React + Vite and can be deployed to any static hosting service.

## 📦 Building for Production

```bash
npm run build
```

This creates an optimized production build in the `dist` folder.

## 🌐 Deployment Options

### Option 1: Vercel (Recommended)

**Why Vercel?**
- Zero configuration
- Automatic deployments from Git
- Built-in CDN
- Free SSL certificate
- Great performance

**Steps:**

1. Install Vercel CLI:
```bash
npm install -g vercel
```

2. Deploy:
```bash
vercel
```

3. Follow the prompts to link your project

**Or use the Vercel website:**
1. Go to [vercel.com](https://vercel.com)
2. Import your Git repository
3. Vercel auto-detects Vite configuration
4. Click "Deploy"

### Option 2: Netlify

**Steps:**

1. Install Netlify CLI:
```bash
npm install -g netlify-cli
```

2. Build the project:
```bash
npm run build
```

3. Deploy:
```bash
netlify deploy --prod --dir=dist
```

**Or use Netlify website:**
1. Go to [netlify.com](https://netlify.com)
2. Drag and drop the `dist` folder
3. Or connect your Git repository for automatic deployments

**Build settings:**
- Build command: `npm run build`
- Publish directory: `dist`

### Option 3: GitHub Pages

1. Install gh-pages:
```bash
npm install --save-dev gh-pages
```

2. Add to `package.json`:
```json
{
  "scripts": {
    "predeploy": "npm run build",
    "deploy": "gh-pages -d dist"
  },
  "homepage": "https://yourusername.github.io/ooty-coffee-estates"
}
```

3. Update `vite.config.js`:
```javascript
export default defineConfig({
  base: '/ooty-coffee-estates/', // your repo name
  plugins: [react()],
})
```

4. Deploy:
```bash
npm run deploy
```

### Option 4: Firebase Hosting

1. Install Firebase CLI:
```bash
npm install -g firebase-tools
```

2. Login to Firebase:
```bash
firebase login
```

3. Initialize Firebase:
```bash
firebase init hosting
```

4. Configure:
   - Public directory: `dist`
   - Single-page app: Yes
   - Don't overwrite index.html

5. Build and deploy:
```bash
npm run build
firebase deploy
```

### Option 5: AWS S3 + CloudFront

1. Build the project:
```bash
npm run build
```

2. Create an S3 bucket:
   - Enable static website hosting
   - Make bucket public

3. Upload `dist` folder contents to S3

4. Configure CloudFront:
   - Create distribution pointing to S3
   - Set default root object to `index.html`
   - Configure error pages (404 → index.html)

5. Update DNS to point to CloudFront

### Option 6: Traditional Web Hosting (cPanel, etc.)

1. Build the project:
```bash
npm run build
```

2. Upload contents of `dist` folder to your web host:
   - Via FTP/SFTP
   - Or cPanel File Manager

3. Ensure your server is configured to:
   - Serve `index.html` for all routes (for SPA routing)
   - Enable gzip compression
   - Set proper cache headers

## 🔧 Environment Configuration

### Production Environment Variables

Create `.env.production`:

```env
VITE_API_URL=https://api.ootycoffee.com
VITE_GA_ID=G-XXXXXXXXXX
```

Access in code:
```javascript
const apiUrl = import.meta.env.VITE_API_URL;
```

## 🎯 Post-Deployment Checklist

- [ ] Test on mobile devices
- [ ] Verify all images load correctly
- [ ] Check all links work
- [ ] Test form submissions (newsletter)
- [ ] Verify GSAP animations work smoothly
- [ ] Check page load speed (use Lighthouse)
- [ ] Test on different browsers (Chrome, Firefox, Safari)
- [ ] Verify SSL certificate is working
- [ ] Set up custom domain (if applicable)
- [ ] Configure CDN for better performance
- [ ] Set up analytics (Google Analytics, etc.)
- [ ] Submit sitemap to search engines

## 📊 Performance Optimization

### After Deployment:

1. **Enable Compression**
   - Gzip/Brotli compression on server
   - Most modern hosts enable this by default

2. **Cache Headers**
   - Set long cache times for static assets
   - Use versioned filenames (Vite does this automatically)

3. **CDN Configuration**
   - Images should be served from CDN
   - Consider using Cloudflare for free CDN

4. **Image Optimization**
   - Ensure all images are WebP format
   - Use appropriate sizes for different devices
   - Implement lazy loading (already done in code)

5. **Monitor Performance**
   - Use Google Lighthouse
   - Check Core Web Vitals
   - Monitor with tools like Vercel Analytics or Google Analytics

## 🔒 Security Best Practices

- [ ] Enable HTTPS (SSL certificate)
- [ ] Set security headers:
  - Content-Security-Policy
  - X-Frame-Options
  - X-Content-Type-Options
- [ ] Configure CORS if needed
- [ ] Regularly update dependencies
- [ ] Use environment variables for sensitive data

## 🌍 Custom Domain Setup

### For Vercel:
1. Go to project settings
2. Add custom domain
3. Update DNS records with your domain provider
4. Vercel handles SSL automatically

### For Netlify:
1. Go to domain settings
2. Add custom domain
3. Update DNS records
4. SSL certificate is auto-provisioned

### DNS Configuration:
```
Type: A
Name: @
Value: [Your host IP]

Type: CNAME
Name: www
Value: [Your domain]
```

## 📱 Progressive Web App (Optional)

To make the site installable as a PWA:

1. Add a manifest file
2. Implement service worker
3. Add offline functionality
4. Test with Lighthouse PWA audit

## 🐛 Troubleshooting

### Build Errors:
- Clear node_modules: `rm -rf node_modules && npm install`
- Clear build cache: `rm -rf dist`
- Update dependencies: `npm update`

### Deployment Issues:
- Check build logs for errors
- Verify all environment variables are set
- Ensure `dist` folder is being uploaded
- Check server configuration for SPA routing

### Performance Issues:
- Optimize images (reduce file sizes)
- Enable lazy loading
- Use CDN for assets
- Minimize CSS/JS (Vite does this automatically)

## 📞 Support Resources

- [Vite Documentation](https://vitejs.dev/)
- [Vercel Documentation](https://vercel.com/docs)
- [Netlify Documentation](https://docs.netlify.com/)
- [GSAP Documentation](https://greensock.com/docs/)
- [React Documentation](https://react.dev/)

## 🎉 Next Steps After Deployment

1. **Set up Analytics**
   - Google Analytics
   - Hotjar for heatmaps
   - Vercel/Netlify Analytics

2. **Configure SEO**
   - Submit sitemap to Google Search Console
   - Add structured data
   - Optimize meta tags

3. **Monitor Performance**
   - Set up uptime monitoring
   - Track Core Web Vitals
   - Monitor error logs

4. **Marketing**
   - Share on social media
   - Submit to directories
   - Start content marketing

5. **Continuous Improvement**
   - Gather user feedback
   - A/B test different versions
   - Regularly update content
   - Add new features

Good luck with your deployment! ☕
