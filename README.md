# Bosker Excavating & Trucking Website

Business website for Bosker Excavating and Trucking, built with [Astro](https://astro.build) v6.1.

## Local Development

```bash
# Install dependencies
npm install

# Start dev server (http://localhost:4321)
npm run dev

# Build for production
npm run build

# Preview the production build
npm run preview
```

---

## Deploying to GitHub Pages (Step-by-Step)

This guide assumes you're starting from scratch with no GitHub repository yet.

### 1. Create a GitHub Account (skip if you already have one)

Go to [github.com](https://github.com) and sign up for a free account.

### 2. Install Git (skip if already installed)

Check if Git is installed by opening your terminal and running:

```bash
git --version
```

If it's not installed, download it from [git-scm.com](https://git-scm.com/downloads) and follow the installer.

### 3. Configure Git (one-time setup)

Set your name and email so Git knows who you are:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

### 4. Create a GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Name the repository: `bosker-excavating`
3. Leave it set to **Public**
4. Do **NOT** check "Add a README file" (we already have one)
5. Click **Create repository**

### 5. Update the Astro Config

Open `astro.config.mjs` and update the `site` value with your actual GitHub username:

```js
export default defineConfig({
  site: 'https://YOUR-GITHUB-USERNAME.github.io',
  base: '/bosker-excavating',
});
```

Replace `YOUR-GITHUB-USERNAME` with your actual GitHub username (e.g., `johndoe`).

### 6. Initialize Git and Push to GitHub

Run these commands from inside the `bosker-excavating` folder:

```bash
# Initialize a new git repository
git init

# Add all files
git add .

# Create your first commit
git commit -m "Initial commit: Bosker Excavating website"

# Set the branch name to main
git branch -M main

# Connect to your GitHub repository (replace YOUR-USERNAME)
git remote add origin https://github.com/YOUR-USERNAME/bosker-excavating.git

# Push your code to GitHub
git push -u origin main
```

### 7. Enable GitHub Pages

1. Go to your repository on GitHub: `https://github.com/YOUR-USERNAME/bosker-excavating`
2. Click **Settings** (the gear icon tab at the top)
3. In the left sidebar, click **Pages**
4. Under **Source**, select **GitHub Actions**
5. That's it — the included workflow file (`.github/workflows/deploy.yml`) will handle the rest automatically

### 8. Wait for Deployment

1. Go to the **Actions** tab in your repository
2. You should see a workflow running called "Deploy to GitHub Pages"
3. Wait for it to finish (usually takes 1-2 minutes)
4. Once it shows a green checkmark, your site is live!

### 9. Visit Your Site

Your website will be available at:

```
https://YOUR-USERNAME.github.io/bosker-excavating/
```

---

## Making Changes

Whenever you want to update the site:

1. Edit the files locally
2. Run `npm run dev` to preview changes
3. When happy, commit and push:

```bash
git add .
git commit -m "Describe what you changed"
git push
```

The site will automatically rebuild and redeploy within a couple minutes.

## Using a Custom Domain (Optional)

If you want to use a custom domain like `boskerexcavating.com`:

1. Buy a domain from a registrar (Namecheap, Google Domains, GoDaddy, etc.)
2. In your GitHub repo, go to **Settings > Pages**
3. Under **Custom domain**, enter your domain and click **Save**
4. At your domain registrar, add a **CNAME** record pointing to `YOUR-USERNAME.github.io`
5. Update `astro.config.mjs`:

```js
export default defineConfig({
  site: 'https://boskerexcavating.com',
  base: '/',
});
```

6. Commit and push the change

## Project Structure

```
bosker-excavating/
├── src/
│   ├── layouts/
│   │   └── BaseLayout.astro    # Shared header, footer, nav
│   ├── pages/
│   │   ├── index.astro         # Homepage
│   │   ├── services.astro      # Services page
│   │   └── contact.astro       # Contact page
│   └── styles/
│       └── global.css          # Global styles
├── public/                     # Static assets (favicon, images)
├── .github/workflows/
│   └── deploy.yml              # GitHub Pages auto-deploy
├── astro.config.mjs            # Astro configuration
└── package.json
```
