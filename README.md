# Dhruval Patel - Portfolio Website

A modern, responsive portfolio website showcasing my work, skills, and projects.

## Features

- 🎨 Modern and clean design
- 📱 Fully responsive (mobile, tablet, desktop)
- ⚡ Fast and lightweight
- 🎯 Smooth scrolling navigation
- 💼 Project showcase section
- 📧 Contact form
- 🌐 Ready for GitHub Pages hosting

## Technologies Used

- HTML5
- CSS3 (with CSS Grid and Flexbox)
- Vanilla JavaScript
- Font Awesome Icons

## Getting Started

### Local Development

1. Clone this repository:
```bash
git clone https://github.com/yourusername/portfolio.git
cd portfolio
```

2. Open `index.html` in your web browser, or use a local server:
```bash
# Using Python
python -m http.server 8000

# Using Node.js (http-server)
npx http-server
```

3. Visit `http://localhost:8000` in your browser

## Deployment to GitHub Pages

1. Push your code to a GitHub repository

2. Go to your repository on GitHub

3. Navigate to **Settings** → **Pages**

4. Under **Source**, select the branch you want to deploy (usually `main` or `master`)

5. Select the folder (usually `/root`)

6. Click **Save**

7. Your site will be live at: `https://yourusername.github.io/repository-name`

## Custom Domain Setup (dhruvalpatel.net)

This repository includes a `CNAME` file configured for `dhruvalpatel.net`. Follow these steps to connect your custom domain:

### Step 1: Configure GitHub Pages

1. Go to your repository on GitHub
2. Navigate to **Settings** → **Pages**
3. Under **Custom domain**, enter: `dhruvalpatel.net`
4. Check **Enforce HTTPS** (recommended)
5. Click **Save**

GitHub will automatically create/update the `CNAME` file in your repository.

### Step 2: Configure DNS Records

You need to configure DNS records with your domain registrar (where you purchased `dhruvalpatel.net`). Add the following records:

#### Option A: Apex Domain (dhruvalpatel.net) - Recommended

Add these **A records**:
```
Type: A
Name: @ (or leave blank)
Value: 185.199.108.153
TTL: 3600 (or default)

Type: A
Name: @ (or leave blank)
Value: 185.199.109.153
TTL: 3600 (or default)

Type: A
Name: @ (or leave blank)
Value: 185.199.110.153
TTL: 3600 (or default)

Type: A
Name: @ (or leave blank)
Value: 185.199.111.153
TTL: 3600 (or default)
```

#### Option B: Subdomain (www.dhruvalpatel.net)

Add this **CNAME record**:
```
Type: CNAME
Name: www
Value: yourusername.github.io
TTL: 3600 (or default)
```

#### Option C: Both (Recommended for best compatibility)

Add all records from Option A (for apex domain) AND Option B (for www subdomain).

### Step 3: Wait for DNS Propagation

- DNS changes can take anywhere from a few minutes to 48 hours to propagate
- You can check DNS propagation status using tools like:
  - [whatsmydns.net](https://www.whatsmydns.net/)
  - [dnschecker.org](https://dnschecker.org/)

### Step 4: Verify SSL Certificate

1. After DNS propagates, GitHub will automatically provision an SSL certificate
2. This usually takes a few minutes to a few hours
3. Once ready, enable **Enforce HTTPS** in GitHub Pages settings

### Step 5: Test Your Site

Visit:
- `http://dhruvalpatel.net` (should redirect to HTTPS)
- `https://dhruvalpatel.net`
- `https://www.dhruvalpatel.net`

### Troubleshooting

**If your domain doesn't work:**
1. Verify DNS records are correct using `dig` or online DNS checkers
2. Ensure the `CNAME` file exists in your repository root
3. Check that GitHub Pages is enabled and pointing to the correct branch
4. Wait for DNS propagation (can take up to 48 hours)
5. Clear your browser cache and try again

**If HTTPS doesn't work:**
- Wait a few hours for GitHub to provision the SSL certificate
- Ensure "Enforce HTTPS" is enabled in GitHub Pages settings
- Check that your DNS records are correctly configured

### Squarespace Integration (Optional)

If you're using Squarespace for other parts of your site:

1. **Subdomain approach**: Host this portfolio on a subdomain like `portfolio.dhruvalpatel.net` or `www.dhruvalpatel.net`
2. **Squarespace domain**: Keep your main Squarespace site on `dhruvalpatel.net`
3. **GitHub Pages subdomain**: Set up `portfolio.dhruvalpatel.net` pointing to GitHub Pages

To set up a subdomain:
1. Create a new `CNAME` file with: `portfolio.dhruvalpatel.net`
2. Add a CNAME DNS record:
   ```
   Type: CNAME
   Name: portfolio
   Value: yourusername.github.io
   TTL: 3600
   ```

## Customization

### Update Personal Information

1. **Name and Title**: Edit the hero section in `index.html`
2. **About Section**: Update the about text in the About section
3. **Skills**: Modify the skills in the Skills section
4. **Projects**: Update project cards with your actual projects
5. **Contact**: Update email, phone, and social media links

### Update Social Media Links

Edit the social media links in:
- Hero section (`.social-links`)
- Footer (`.footer-social`)

Replace the placeholder URLs with your actual profiles.

### Update Contact Form

The contact form currently shows an alert. To make it functional:

1. Set up a backend service (e.g., Formspree, EmailJS, or your own API)
2. Update the form submission handler in `script.js`

### Change Colors

Edit the CSS variables in `styles.css`:

```css
:root {
    --primary-color: #6366f1;
    --secondary-color: #8b5cf6;
    /* ... other variables */
}
```

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## License

This project is open source and available under the [MIT License](LICENSE).

## Contact

Dhruval Patel
- Email: dhruval@example.com
- GitHub: [@yourusername](https://github.com/yourusername)

---

Made with ❤️ by Dhruval Patel

