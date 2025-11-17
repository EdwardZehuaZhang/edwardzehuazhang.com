# Vercel Deployment Guide

## Quick Deploy

### Method 1: One-Click Deploy (Recommended)
1. Go to [Vercel](https://vercel.com)
2. Sign in with your GitHub account
3. Click "Add New Project"
4. Import `EdwardZehuaZhang/edwardzehuazhang.com` repository
5. Configure the project:
   - **Framework Preset**: Other (or leave as detected)
   - **Root Directory**: `./`
   - **Build Command**: Leave empty (static site)
   - **Output Directory**: Leave empty
6. Click "Deploy"

### Method 2: Using Vercel CLI

1. **Install Vercel CLI**
   ```bash
   npm install -g vercel
   ```

2. **Login to Vercel**
   ```bash
   vercel login
   ```

3. **Deploy from project directory**
   ```bash
   cd "d:\Coding Files\GitHub\edwardzehuazhang.com"
   vercel
   ```

4. **Follow the prompts:**
   - Set up and deploy? `Y`
   - Which scope? (Select your account)
   - Link to existing project? `N`
   - What's your project's name? `edwardzehuazhang`
   - In which directory is your code located? `./`
   - Want to override the settings? `N`

5. **Deploy to production**
   ```bash
   vercel --prod
   ```

## Configuration

### vercel.json (Optional)
Create a `vercel.json` file in your project root for custom configuration:

```json
{
  "cleanUrls": true,
  "trailingSlash": false,
  "rewrites": [
    { "source": "/", "destination": "/page.html" },
    { "source": "/writing/design-tokens-101", "destination": "/writing/design-tokens-101/page.html" },
    { "source": "/writing/hello-world", "destination": "/writing/hello-world/page.html" },
    { "source": "/writing/how-ai-is-changing-my-workflow", "destination": "/writing/how-ai-is-changing-my-workflow/page.html" },
    { "source": "/writing/how-to-think-like-both-a-designer-engineer", "destination": "/writing/how-to-think-like-both-a-designer-engineer/page.html" },
    { "source": "/writing/ui-performance", "destination": "/writing/ui-performance/page.html" }
  ]
}
```

## Custom Domain Setup

1. Go to your project on Vercel Dashboard
2. Click "Settings" → "Domains"
3. Add your custom domain (e.g., `edwardzehuazhang.com`)
4. Configure DNS records as instructed:
   - **A Record**: Point to Vercel's IP: `76.76.21.21`
   - **CNAME Record** (www): Point to `cname.vercel-dns.com`
5. Wait for DNS propagation (can take up to 48 hours)

## Automatic Deployments

Vercel automatically deploys:
- **Production**: When you push to the `main` branch
- **Preview**: For every pull request and branch push

## Environment Variables

If your site needs environment variables:
1. Go to Project Settings → Environment Variables
2. Add key-value pairs
3. Select which environments (Production, Preview, Development)
4. Redeploy if needed

## Site Details

- **Site Type**: Static HTML Portfolio
- **Main File**: `page.html`
- **Framework**: Framer-generated static site
- **Google Analytics**: Already configured (G-H147LZ64H2)

## Useful Commands

```bash
# Deploy to preview
vercel

# Deploy to production
vercel --prod

# Check deployment logs
vercel logs

# Open project in browser
vercel open
```

## Troubleshooting

### Site shows 404
- Ensure `page.html` is in the root directory
- Check if rewrites in `vercel.json` are correct

### Changes not showing
- Clear cache: `vercel --force`
- Check deployment logs in Vercel dashboard

### Build errors
- This is a static site, no build required
- Remove any build commands if added

## Support

- [Vercel Documentation](https://vercel.com/docs)
- [Vercel Support](https://vercel.com/support)
- [Vercel Community](https://github.com/vercel/vercel/discussions)
