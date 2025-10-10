# Find Your AI Buddy

This project hosts a landing page at `/start` for the AI companion service.

## Structure

```
public/
  start/
    index.html    # Main landing page
    terms.html    # Terms of Service
    privacy.html  # Privacy Policy
  _redirects      # Cloudflare Pages routing configuration
```

## Deployment to Cloudflare Pages

### Option 1: Automatic Git Deployment

1. Push this repository to GitHub/GitLab
2. Go to [Cloudflare Dashboard](https://dash.cloudflare.com/)
3. Navigate to **Workers & Pages** → **Create Application** → **Pages** → **Connect to Git**
4. Select your repository
5. Configure build settings:
   - **Build command:** (leave empty for static site)
   - **Build output directory:** `public`
6. Click **Save and Deploy**

### Option 2: Direct Upload via Wrangler CLI

```bash
# Install Wrangler CLI
npm install -g wrangler

# Login to Cloudflare
wrangler login

# Deploy to Cloudflare Pages
wrangler pages deploy public --project-name=findyouraibuddy
```

### Option 3: Drag & Drop Upload

1. Go to [Cloudflare Dashboard](https://dash.cloudflare.com/)
2. Navigate to **Workers & Pages** → **Create Application** → **Pages** → **Upload assets**
3. Drag and drop the `public` folder
4. Set project name: `findyouraibuddy`
5. Click **Save and Deploy**

## Local Testing

To test locally, you can use any static file server:

```bash
# Using Python
cd public
python3 -m http.server 8080

# Using Node.js http-server
npx http-server public -p 8080

# Using Wrangler
wrangler pages dev public
```

Then visit: `http://localhost:8080/start`

## Custom Domain Setup

After deployment, you can add a custom domain in Cloudflare Pages:

1. Go to your Pages project in Cloudflare Dashboard
2. Click **Custom domains**
3. Add your domain
4. Follow DNS configuration instructions

## Features

- Responsive design that works on mobile, tablet, and desktop
- Smooth animations and modern gradient background
- Analytics tracking (Google Analytics, Facebook Pixel, TikTok Pixel)
- SEO-friendly meta tags
- Terms of Service and Privacy Policy pages

## Analytics IDs

The site includes tracking for:
- **Google Analytics:** AW-17612351837
- **Facebook Pixel:** 2641698042845279
- **TikTok Pixel:** D3J1SLRC77U7D8VS7HQG

To update these, edit the tracking scripts in `public/start/index.html`.
