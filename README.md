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
