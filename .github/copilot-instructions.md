# GenAI Coach Jekyll Website

GenAI Coach is a Jekyll-based GitHub Pages website for AI training and coaching. The site uses Ruby, Jekyll, Tailwind CSS, and Git Large File Storage (LFS) for handling AI/ML assets.

Always reference these instructions first and fallback to search or bash commands only when you encounter unexpected information that does not match the info here.

## Working Effectively

### Prerequisites and Environment Setup
- Ensure Ruby is available: `ruby --version` (should be 3.2.3+)
- Install bundler: `sudo gem install bundler`
- Verify Git LFS: `git lfs --version` (should be 3.7.0+)

### Initial Repository Setup
**NEVER SKIP THESE STEPS when working with this repository:**
```bash
# Clone and setup (first time only)
git clone https://github.com/genai-coach/ai.git
cd ai
git lfs install
git lfs pull

# Install dependencies - NEVER CANCEL: Takes 2-3 minutes initially
sudo bundle install  # Set timeout to 10+ minutes
```

### Core Development Commands
**Build the site:**
```bash
bundle exec jekyll build  # Takes ~1-2 seconds. Safe to run frequently.
```

**Serve locally for development:**
```bash
bundle exec jekyll serve --host 0.0.0.0 --port 4000  # Serves instantly
```
- Site available at: `http://localhost:4000/ai/` (note the `/ai/` baseurl)
- Use Ctrl+C to stop the server

**Incremental development:**
```bash
bundle exec jekyll serve --host 0.0.0.0 --port 4000 --incremental --watch
```

### Git LFS Operations
**Check LFS status:**
```bash
git lfs status          # Check tracked files
git lfs ls-files        # List all LFS files
git lfs track           # Show tracking patterns
```

**Add large files:**
```bash
git lfs track "path/to/large-file.pt"  # Manual tracking if needed
git add .gitattributes                  # Commit tracking changes
git add your-large-file.pt
git commit -m "Add AI model file"
git push
```

## Validation

### Required Validation Steps
**ALWAYS perform these validations after making changes:**

1. **Build Validation:**
   ```bash
   bundle exec jekyll build
   ```
   - Must complete without errors
   - Should finish in 1-2 seconds

2. **Local Site Testing:**
   ```bash
   bundle exec jekyll serve --host 0.0.0.0 --port 4000
   ```
   - Access `http://localhost:4000/ai/`
   - Verify homepage loads with GenAI Coach branding
   - Navigate to `/about/` page
   - Check that CSS styles render correctly
   - Confirm responsive design works

3. **Content Validation:**
   - Homepage should show hero section with "Master the Future of AI with GenAI Coach"
   - About page should load instructor information (Stefano Vincenti from IT University of Copenhagen)
   - Navigation links should work between pages
   - All images and icons should render
   - Footer should show copyright and contact information

### Manual Testing Scenarios
**CRITICAL: Always manually validate these complete scenarios after changes:**

**Scenario 1: Fresh Clone Workflow**
```bash
# Simulate fresh repository clone
rm -rf /tmp/ai-test
cd /tmp
git clone https://github.com/genai-coach/ai.git ai-test
cd ai-test
git lfs install
git lfs pull
sudo bundle install
bundle exec jekyll build
bundle exec jekyll serve --host 0.0.0.0 --port 4001 &
sleep 3
curl -I http://localhost:4001/ai/  # Should return 200 OK
pkill -f "jekyll serve"
```

**Scenario 2: Content Update Workflow**
```bash
# Make a small content change
echo "<!-- Test comment $(date) -->" >> index.md
bundle exec jekyll build  # Should succeed
bundle exec jekyll serve --host 0.0.0.0 --port 4000 &
sleep 2
curl http://localhost:4000/ai/ | grep -q "GenAI Coach"  # Should find content
pkill -f "jekyll serve"
git checkout -- index.md  # Revert test change
```

## Common Tasks

### File Structure Reference
**Repository root:**
```
.
├── .git/                 # Git repository
├── .gitattributes        # LFS file patterns
├── .gitignore           # Jekyll and Ruby ignores
├── .lfsconfig           # LFS configuration  
├── Gemfile              # Ruby dependencies
├── Gemfile.lock         # Locked dependency versions
├── README.md            # LFS setup documentation
├── _config.yml          # Jekyll configuration
├── _layouts/            # HTML templates
│   └── default.html     # Main page layout
├── _pages/              # Site pages
│   ├── about.md         # About page
│   └── _projects/       # Project pages
├── _site/               # Generated site (do not edit)
├── assets/              # CSS, images, etc.
│   └── css/
└── index.md             # Homepage content
```

### Key Configuration Files

**_config.yml contents:**
```yaml
title: GenAI Coach
description: AI Training and Coaching platform
repository: genai-coach/ai
url: https://genai-coach.github.io/ai/
baseurl: "/ai"
plugins: [jekyll-remote-theme, jekyll-tailwindcss, ...]
```

**Gemfile dependencies:**
```ruby
gem "github-pages", group: :jekyll_plugins
gem "jekyll-remote-theme"
gem "jekyll-tailwindcss" 
gem "webrick"
```

### Working with Content
**Edit homepage:** Modify `index.md`
**Edit about page:** Modify `_pages/about.md`  
**Add new pages:** Create `.md` files in `_pages/`
**Modify layout:** Edit `_layouts/default.html`
**Update styles:** Edit `assets/css/tailwind.css`

**After content changes, ALWAYS:**
1. Build: `bundle exec jekyll build`
2. Test locally: `bundle exec jekyll serve` then check `localhost:4000/ai/`
3. Verify the change appears correctly

### Git LFS File Patterns
**Automatically tracked by LFS:**
- AI/ML models: `*.pt`, `*.pth`, `*.h5`, `*.pkl`, `*.bin`, `*.onnx`
- Datasets: `*.parquet`, `*.feather`, `*.arrow`, `*.hdf`  
- Media: `*.mp4`, `*.avi`, `*.wav`, `*.mp3`, `*.flac`
- Archives: `*.zip`, `*.tar.gz`, `*.7z`

### Troubleshooting
**Bundle install fails:** Run `sudo bundle install`
**Site not loading:** Check you're using `localhost:4000/ai/` (with /ai/ path)
**LFS files missing:** Run `git lfs pull`
**Build errors:** Check `_config.yml` syntax and Gemfile dependencies

### Timing Expectations
- **Bundle install (first time):** 2-3 minutes - NEVER CANCEL, set 10+ minute timeout
- **Bundle install (updates):** 30-60 seconds
- **Jekyll build:** 1-2 seconds - very fast, safe to run frequently  
- **Jekyll serve startup:** Instant - should be ready in under 5 seconds
- **LFS pull:** Depends on file sizes - could be seconds to minutes
- **Repository clone:** 10-30 seconds for this repository

### Important Notes
- This is a documentation site - no automated tests or linting exist
- GitHub Pages automatically builds from main branch
- Always use baseurl `/ai/` when testing locally
- LFS is critical - many AI/ML files won't work without it
- The site uses custom CSS embedded in `_layouts/default.html`
- Tailwind CSS is loaded via CDN in the layout file
- Bundle install may show "Don't run Bundler as root" warning - this is normal and safe to ignore
- Faraday retry gem warning during build is harmless - site builds successfully