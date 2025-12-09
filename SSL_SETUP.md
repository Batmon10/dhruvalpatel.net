# Fixing "Not Secure" Warning on dhruvalpatel.net

## Why You're Seeing "Not Secure"

The "Not secure" warning appears because:
1. GitHub Pages hasn't provisioned the SSL certificate yet (can take 10 minutes to 24 hours)
2. "Enforce HTTPS" might not be enabled in GitHub Pages settings
3. DNS records might not be fully propagated

## Step-by-Step Fix

### Step 1: Verify GitHub Pages Settings

1. Go to your GitHub repository: `https://github.com/Batmon10/YOUR_REPO_NAME`
2. Click **Settings** → **Pages**
3. Under **Custom domain**, verify it shows: `dhruvalpatel.net`
4. **IMPORTANT**: Check the box for **"Enforce HTTPS"**
5. Click **Save**

### Step 2: Verify DNS Configuration

Make sure your DNS records are correctly set up at your domain registrar:

**For Apex Domain (dhruvalpatel.net):**
```
Type: A
Host: @ (or blank)
Value: 185.199.108.153
TTL: 3600

Type: A
Host: @ (or blank)
Value: 185.199.109.153
TTL: 3600

Type: A
Host: @ (or blank)
Value: 185.199.110.153
TTL: 3600

Type: A
Host: @ (or blank)
Value: 185.199.111.153
TTL: 3600
```

**For WWW Subdomain (www.dhruvalpatel.net):**
```
Type: CNAME
Host: www
Value: Batmon10.github.io
TTL: 3600
```

### Step 3: Wait for SSL Certificate

After enabling "Enforce HTTPS":
- GitHub will automatically request an SSL certificate from Let's Encrypt
- This process typically takes **10 minutes to 1 hour**
- In some cases, it can take up to **24 hours**

### Step 4: Check Certificate Status

1. Visit: `https://www.ssllabs.com/ssltest/analyze.html?d=dhruvalpatel.net`
2. This will show if the SSL certificate is active

### Step 5: Clear Browser Cache

After the certificate is provisioned:
1. Clear your browser cache
2. Try accessing the site in an incognito/private window
3. Visit: `https://dhruvalpatel.net` (make sure to use HTTPS)

## Troubleshooting

### If "Enforce HTTPS" is Grayed Out

This means GitHub hasn't detected your custom domain yet. Check:
- ✅ DNS records are correctly configured
- ✅ DNS has propagated (check at https://www.whatsmydns.net/)
- ✅ You've waited at least 10 minutes after adding the custom domain

### If Certificate Takes Too Long

1. **Remove and re-add the custom domain:**
   - In GitHub Pages settings, remove `dhruvalpatel.net`
   - Wait 5 minutes
   - Add it back and enable "Enforce HTTPS"

2. **Check DNS propagation:**
   - Visit: https://www.whatsmydns.net/#A/dhruvalpatel.net
   - All locations should show the GitHub IP addresses

3. **Verify CNAME file:**
   - Make sure `CNAME` file exists in your repository root
   - It should contain: `dhruvalpatel.net`

### If Still Not Working After 24 Hours

1. Contact GitHub Support
2. Verify your domain registrar isn't blocking GitHub's certificate requests
3. Check if your domain has any special DNS requirements

## Quick Checklist

- [ ] Custom domain added in GitHub Pages settings
- [ ] "Enforce HTTPS" checkbox is enabled (not grayed out)
- [ ] DNS A records point to GitHub IPs (185.199.108.153, etc.)
- [ ] DNS CNAME record for www points to Batmon10.github.io
- [ ] CNAME file exists in repository root
- [ ] Waited at least 10 minutes after enabling HTTPS
- [ ] Cleared browser cache
- [ ] Accessing site via HTTPS (not HTTP)

## Expected Timeline

- **DNS Propagation**: 5 minutes to 24 hours
- **SSL Certificate Provisioning**: 10 minutes to 1 hour (usually)
- **Full HTTPS Activation**: Up to 24 hours in rare cases

Once the SSL certificate is active, the "Not secure" warning will disappear and you'll see a padlock icon in the browser address bar.

---

**Note**: If you're testing locally (localhost), you'll always see "Not secure" - this is normal and only applies to the live domain.

