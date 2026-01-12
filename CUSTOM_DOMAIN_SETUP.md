# Custom Domain Setup for GitHub Pages

This guide will help you set up a professional custom domain (like `ankitagurjar.com` or `ankita.design`) for your portfolio instead of using the default `roshangurjar275.github.io/Ankita_Portfolio` URL.

## Option 1: Using a Custom Domain (Recommended for Professional Portfolio)

### Step 1: Purchase a Domain
1. Choose a domain registrar (popular options):
   - **Namecheap** (https://www.namecheap.com) - User-friendly, good prices
   - **Google Domains** (https://domains.google) - Simple interface
   - **GoDaddy** (https://www.godaddy.com) - Widely used
   - **Cloudflare** (https://www.cloudflare.com/products/registrar) - Best prices, includes free privacy

2. Search for and purchase your desired domain:
   - Examples: `ankitagurjar.com`, `ankitagurjar.design`, `ankita-gurjar.com`
   - `.com` is most professional, but `.design` or `.portfolio` can be creative alternatives

### Step 2: Configure GitHub Pages with Custom Domain

1. **In your GitHub repository:**
   - Go to **Settings** → **Pages** (left sidebar)
   - Under "Custom domain", enter your domain (e.g., `ankitagurjar.com`)
   - Check **"Enforce HTTPS"** (recommended for security)
   - Click **Save**

2. **GitHub will create a `CNAME` file automatically:**
   - This file will contain your domain name
   - It will be committed to your repository

### Step 3: Configure DNS Records at Your Domain Registrar

You need to add DNS records to point your domain to GitHub Pages. Choose **ONE** of these methods:

#### Method A: Apex Domain (ankitagurjar.com) - Recommended

If you want `ankitagurjar.com` (without www):

1. Go to your domain registrar's DNS management page
2. Add these **A records** (replace with GitHub's current IPs - check GitHub docs for latest):
   ```
   Type: A
   Name: @ (or leave blank)
   Value: 185.199.108.153
   TTL: 3600 (or default)
   
   Type: A
   Name: @ (or leave blank)
   Value: 185.199.109.153
   TTL: 3600
   
   Type: A
   Name: @ (or leave blank)
   Value: 185.199.110.153
   TTL: 3600
   
   Type: A
   Name: @ (or leave blank)
   Value: 185.199.111.153
   TTL: 3600
   ```

3. **Also add a CNAME record for www subdomain:**
   ```
   Type: CNAME
   Name: www
   Value: roshangurjar275.github.io
   TTL: 3600
   ```

#### Method B: www Subdomain (www.ankitagurjar.com)

If you prefer `www.ankitagurjar.com`:

1. Add a **CNAME record**:
   ```
   Type: CNAME
   Name: www
   Value: roshangurjar275.github.io
   TTL: 3600
   ```

2. In GitHub Pages settings, set custom domain to `www.ankitagurjar.com`

### Step 4: Wait for DNS Propagation

- DNS changes can take **15 minutes to 48 hours** to propagate
- You can check propagation status at: https://www.whatsmydns.net
- Once propagated, your custom domain will work!

### Step 5: Verify HTTPS (Automatic)

- GitHub automatically provisions SSL certificates for custom domains
- After DNS propagates, HTTPS will be enabled automatically
- Make sure "Enforce HTTPS" is checked in GitHub Pages settings

---

## Option 2: Using GitHub's Free Subdomain (Quick Alternative)

If you don't want to purchase a domain, you can:

1. **Rename your repository** to match your desired subdomain:
   - Current: `Ankita_Portfolio`
   - Rename to: `ankitagurjar.github.io` (must match your GitHub username format)
   - Go to **Settings** → **General** → **Repository name** → **Rename**

2. **Move `index.html` to root** (if not already there)

3. **Your site will be available at:**
   - `https://roshangurjar275.github.io/ankitagurjar.github.io` (if you keep current repo name)
   - OR `https://ankitagurjar.github.io` (if you rename repo and create new one with that exact name)

**Note:** For this to work with a clean URL, the repository name must be `username.github.io` where `username` is your GitHub username.

---

## Option 3: Use a Shorter Repository Name

If you want a slightly cleaner URL without buying a domain:

1. **Create a new repository** named `portfolio` or `ankita-portfolio`
2. **Your URL will be:** `https://roshangurjar275.github.io/portfolio`
3. This is shorter and more professional than `/Ankita_Portfolio`

---

## Recommended Domain Names for Your Portfolio

Based on your name "Ankita Gurjar", here are some professional options:

- `ankitagurjar.com` ⭐ (Most professional)
- `ankita-gurjar.com`
- `ankitagurjar.design` (Creative, shows you're a designer)
- `ankitagurjar.portfolio`
- `ankita.design` (Short and memorable, if available)

---

## Troubleshooting

### Domain not working after 48 hours?
- Verify DNS records are correct using: https://dnschecker.org
- Check GitHub Pages settings show your domain
- Ensure "Enforce HTTPS" is enabled
- Clear your browser cache

### HTTPS not working?
- Wait 24 hours after DNS propagation
- GitHub automatically provisions SSL certificates
- Make sure "Enforce HTTPS" is checked in settings

### www redirect not working?
- Add both A records (for apex) and CNAME (for www)
- Or configure redirect at your domain registrar

---

## Cost Estimate

- **Domain:** $10-15/year for `.com`, $20-30/year for `.design`
- **GitHub Pages:** FREE (hosting included)
- **SSL Certificate:** FREE (automatic from GitHub)

**Total:** ~$10-30/year for a professional custom domain!

---

## Next Steps After Setup

1. Update any links in your portfolio that reference the old URL
2. Share your new professional URL on:
   - LinkedIn profile
   - Resume/CV
   - Business cards
   - Email signature
3. Test all pages and forms work with the new domain
4. Update Google Apps Script URL if needed (should work automatically)

---

## Quick Reference: GitHub Pages Settings Location

1. Go to: https://github.com/roshangurjar275/Ankita_Portfolio/settings/pages
2. Under "Custom domain", enter your domain
3. Check "Enforce HTTPS"
4. Save

Your site will be live at your custom domain within 24-48 hours!

