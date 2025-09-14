# GenAI Coach

Welcome to GenAI Coach - your premier destination for AI training and coaching.

## About

GenAI Coach connects professionals with cutting-edge AI education and collaborative development opportunities.

## Getting Started

Explore our projects and training materials to begin your AI journey.

## Projects

Browse our collection of AI training projects and resources.

## Working with Large Files (Git LFS)

This repository is configured to use Git Large File Storage (LFS) for handling large AI/ML files. This ensures smooth collaboration when working with models, datasets, and media files.

### Supported File Types

The following file types are automatically tracked by LFS:

**Model Files:**
- `*.model`, `*.pkl`, `*.bin`, `*.h5`, `*.pt`, `*.pth`, `*.onnx`, `*.pb`, `*.tflite`

**Dataset Files:**
- `*.parquet`, `*.feather`, `*.arrow`, `*.hdf`

**Media Files:**
- `*.mp4`, `*.avi`, `*.wav`, `*.mp3`, `*.flac`

**Archive Files:**
- `*.zip`, `*.tar.gz`, `*.7z`

### Setup Instructions

1. **Install Git LFS** (if not already installed):
   ```bash
   git lfs install
   ```

2. **Clone the repository** with LFS support:
   ```bash
   git clone https://github.com/genai-coach/ai.git
   cd ai
   ```

3. **Pull LFS files** (if needed):
   ```bash
   git lfs pull
   ```

### Adding Large Files

When adding large files to the repository:

1. **Automatic tracking**: Files matching the configured patterns in `.gitattributes` will be automatically tracked by LFS.

2. **Manual tracking** for specific files:
   ```bash
   git lfs track "path/to/your/large-file.csv"
   git add .gitattributes
   ```

3. **Commit and push** as usual:
   ```bash
   git add your-large-file.pt
   git commit -m "Add trained model"
   git push
   ```

### Checking LFS Status

- View tracked files: `git lfs ls-files`
- Check LFS status: `git lfs status`
- View tracking patterns: `git lfs track`

### Troubleshooting

If you encounter issues with LFS:

1. Ensure Git LFS is installed: `git lfs version`
2. Verify LFS is initialized: `git lfs install`
3. Check tracking configuration: `cat .gitattributes`

For more information, visit the [Git LFS documentation](https://git-lfs.github.io/).

## Toolchain

| Component | Version / Requirement |
|-----------|-----------------------|
| Ruby      | 3.3 (see `.ruby-version`) |
| Bundler   | Use version that ships with Ruby 3.3 (install/update via `gem install bundler` if needed) |
| Jekyll    | Installed via `bundle install` (see `Gemfile`) |
| Git LFS   | Required for model/data/media assets |

### Local Setup
```bash
ruby -v          # should report 3.3.x
bundle install   # install gems
bundle exec jekyll build
```
If you use a version manager (rbenv/asdf/chruby), it will auto-select 3.3 via `.ruby-version`.

## Style Guide

### Professional Color System

This site uses a professional accessible color palette defined in `assets/css/theme.css`. All colors are organized as CSS custom properties (variables) to ensure consistency and maintainability.

#### Color Token Usage

**✅ Preferred - Use semantic component tokens:**
```css
color: var(--text-primary);
background: var(--button-primary-bg);
border-color: var(--card-border);
```

**✅ Acceptable - Use semantic tokens:**
```css
color: var(--brand-500);
background: var(--surface-secondary);
```

**❌ Avoid - Hard-coded hex values:**
```css
color: #2E74E6;  /* Use var(--brand-500) instead */
background: #FFFFFF;  /* Use var(--surface-primary) instead */
```

#### Available Token Categories

- **Brand Colors**: `--brand-50` through `--brand-900` (professional blue scale)
- **Semantic Colors**: `--success-500`, `--warning-500`, `--danger-500`, `--info-500`
- **Surface/Background**: `--surface-primary`, `--surface-secondary`, `--surface-tertiary`
- **Text Colors**: `--text-primary`, `--text-secondary`, `--text-tertiary`
- **Component Tokens**: `--button-primary-bg`, `--link-color`, `--card-bg`, etc.

#### Dark Mode Support

The system includes a dark mode implementation using `@media (prefers-color-scheme: dark)` that automatically adjusts colors for better readability.

#### Accessibility Guidelines

- All color combinations maintain WCAG AA contrast ratios (4.5:1 minimum)
- Focus states use `--focus-ring` for keyboard navigation
- Text selection uses high-contrast `--selection-bg` and `--selection-fg`

#### Development Rule

**No new hard-coded hex values** - always use the provided color tokens. If you need a color that doesn't exist, add it to the token system first.
