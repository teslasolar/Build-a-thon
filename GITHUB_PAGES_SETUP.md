# Deploying to GitHub Pages

## Quick Setup

1. **Create a GitHub repository** for your Build-a-thon training materials

2. **Push the code:**
   ```bash
   git init
   git add .
   git commit -m "Initial commit - Build-a-thon 2025 Training Portal"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
   git push -u origin main
   ```

3. **Enable GitHub Pages:**
   - Go to your repository on GitHub
   - Click **Settings** (in the repo navigation)
   - Scroll down to **Pages** in the left sidebar
   - Under "Source", select **Deploy from a branch**
   - Select **main** branch and **/ (root)** folder
   - Click **Save**

4. **Access your site:**
   - Wait 2-5 minutes for the initial deployment
   - Visit: `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/`
   - The portal will load with all your training materials!

## Features that work on GitHub Pages

✅ Interactive navigation  
✅ Progress tracking (using localStorage)  
✅ Countdown timer  
✅ Markdown rendering  
✅ Responsive design  
✅ Direct linking to sections  

## Sharing with your team

Once deployed, share the GitHub Pages URL with your team. They can:
- Access from any device
- Track their individual progress
- No installation required
- Works on mobile devices
- Bookmark specific sections

## Updating content

1. Edit the markdown files locally
2. Commit and push changes:
   ```bash
   git add .
   git commit -m "Updated quiz questions"
   git push
   ```
3. GitHub Pages will automatically update within minutes

## Custom domain (optional)

To use a custom domain like `buildathon.inflexionpoint.com`:
1. Add a `CNAME` file with your domain name
2. Configure DNS settings with your domain provider
3. Enable custom domain in GitHub Pages settings

## Troubleshooting

### Files not loading (Failed to fetch error)

**If testing locally:**
- ❌ Don't open index.html directly (file:// won't work)
- ✅ Use a web server: `python -m http.server 8000`
- ✅ Use VS Code Live Server extension

**If on GitHub Pages:**
1. Check deployment status: Settings → Pages (should show green checkmark)
2. Wait 5-10 minutes for initial deployment
3. Clear browser cache (Ctrl+F5 or Cmd+Shift+R)
4. Check exact URL format: `https://username.github.io/repository-name/`
5. Ensure repository is public (or you have GitHub Pro for private Pages)

### Using the test page

Open `test.html` to verify all files are accessible:
- Local: `http://localhost:8000/test.html`
- GitHub Pages: `https://username.github.io/repo/test.html`

This will show you exactly which files are loading correctly.

### Common issues

| Issue | Cause | Solution |
|-------|-------|----------|
| Failed to fetch | Local file access | Use web server |
| 404 errors | Files not deployed | Wait for deployment |
| Empty content | Markdown parsing error | Check file formatting |
| Old content | Browser cache | Hard refresh (Ctrl+F5) |

## Local development

For local testing before pushing:
- Open `index.html` directly in browser
- Or use VS Code with Live Server extension
- Or any static file server

## Files NOT needed for GitHub Pages

**Already removed:**
- ❌ `start_portal.bat` - Local server script (Windows)
- ❌ `start_portal.sh` - Local server script (Mac/Linux)  
- ❌ `_config.yml` - Jekyll config (using .nojekyll instead)
- ❌ `.github/` folder - Not needed for basic Pages hosting

GitHub Pages will automatically serve your `index.html` and all the markdown files without any server scripts!

## Testing before deployment

Use `test.html` to verify your setup:
1. Start local server: `python -m http.server 8000`
2. Open: `http://localhost:8000/test.html`
3. All files should show green checkmarks
4. If any fail, check the file paths and names
