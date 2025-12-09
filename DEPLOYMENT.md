# Deployment Guide for dhruvalpatel.net

## Quick Setup Steps

### 1. Push to GitHub

```bash
# Initialize git (if not already done)
git init

# Add all files
git add .

# Commit
git commit -m "Initial commit - Portfolio website"

# Add your GitHub repository as remote
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git

# Push to GitHub
git push -u origin main
```

### 2. Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** → **Pages**
3. Under **Source**, select branch: `main` and folder: `/ (root)`
4. Click **Save**

### 3. Configure Custom Domain

1. Still in **Settings** → **Pages**
2. Under **Custom domain**, enter: `dhruvalpatel.net`
3. Check **Enforce HTTPS**
4. Click **Save**

GitHub will automatically create/update the `CNAME` file.

### 4. Configure DNS (at your domain registrar)

#### For Apex Domain (dhruvalpatel.net)

Add these **4 A records**:

```
Type: A
Host: @ (or leave blank)
Value: 185.199.108.153
TTL: 3600

Type: A
Host: @ (or leave blank)
Value: 185.199.109.153
TTL: 3600

Type: A
Host: @ (or leave blank)
Value: 185.199.110.153
TTL: 3600

Type: A
Host: @ (or leave blank)
Value: 185.199.111.153
TTL: 3600
```

#### For WWW Subdomain (www.dhruvalpatel.net)

Add this **CNAME record**:

```
Type: CNAME
Host: www
Value: YOUR_USERNAME.github.io
TTL: 3600
```

**Note:** Replace `YOUR_USERNAME` with your actual GitHub username.

### 5. Wait for DNS Propagation

- Usually takes 5 minutes to 24 hours
- Check status at: https://www.whatsmydns.net/
- Search for: `dhruvalpatel.net` and `www.dhruvalpatel.net`

### 6. Verify SSL Certificate

1. After DNS propagates, wait 10-60 minutes
2. GitHub will automatically provision SSL certificate
3. Visit `https://dhruvalpatel.net` to verify

## Using with Squarespace

If you want to use Squarespace for other content:

### Option 1: Subdomain Setup (Recommended)

- **Squarespace**: `dhruvalpatel.net` (main site)
- **GitHub Pages**: `portfolio.dhruvalpatel.net` (this portfolio)

**Steps:**
1. Update `CNAME` file to: `portfolio.dhruvalpatel.net`
2. Add DNS CNAME record:
   ```
   Type: CNAME
   Host: portfolio
   Value: YOUR_USERNAME.github.io
   TTL: 3600
   ```

### Option 2: Path-based (Advanced)

Use Squarespace's redirect feature to point `/portfolio` to your GitHub Pages site.

## Troubleshooting

### Domain not working?
- ✅ Check DNS records are correct
- ✅ Verify `CNAME` file exists in repository
- ✅ Ensure GitHub Pages is enabled
- ✅ Wait for DNS propagation (up to 48 hours)

### HTTPS not working?
- ✅ Wait for SSL certificate provisioning (10-60 minutes)
- ✅ Enable "Enforce HTTPS" in GitHub Pages settings
- ✅ Clear browser cache

### Still having issues?
- Check GitHub Pages status: https://www.githubstatus.com/
- Verify DNS: https://dnschecker.org/
- Contact GitHub Support if needed

## Testing Checklist

- [ ] Site loads at `https://dhruvalpatel.net`
- [ ] Site loads at `https://www.dhruvalpatel.net`
- [ ] HTTPS is enforced (HTTP redirects to HTTPS)
- [ ] All animations work correctly
- [ ] Mobile responsive design works
- [ ] Contact form functions
- [ ] Social media links work
- [ ] Navigation smooth scrolling works

---

**Need help?** Check the main README.md for more detailed information.

