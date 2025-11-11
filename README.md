# Jonah Shader's Personal Site

Personal website built with Hugo and the [Typo theme](https://github.com/tomfran/typo). Features posts about projects, research articles, and academic publications.

**Live site:** https://jonahshader.github.io

## Workflow

### Creating a New Post

**For a project/research post:**
```bash
hugo new content/posts/my-post-name.md
```

**For a publication:**
```bash
hugo new content/publications/my-paper-name.md
```

This creates a new file with front matter including `draft: true`.

### Working with Drafts

1. **Edit your draft** - Write your content in the created markdown file
2. **Preview locally** - Run the Hugo server with drafts enabled:
   ```bash
   hugo server -D --bind 0.0.0.0 --baseURL http://10.0.0.69:1313
   ```
   - `-D` includes draft posts
   - `--bind 0.0.0.0` allows access from other machines on your network
   - `--baseURL` sets the URL for your local network

3. **View your draft** - Navigate to `http://10.0.0.69:1313` (or `http://localhost:1313` on the same machine)

### Publishing a Post

When you're ready to publish:

1. **Remove draft status** - Edit the post's front matter:
   ```yaml
   draft: false  # or remove the draft line entirely
   ```

2. **Commit and push:**
   ```bash
   git add content/
   git commit -m "Publish: [post title]"
   git push
   ```

3. **Automatic deployment** - GitHub Actions will automatically build and deploy your site to https://jonahshader.github.io

The deployment typically takes 1-2 minutes. You can monitor progress at:
https://github.com/jonahshader/jonahshader.github.io/actions

## Site Structure

```
content/
├── posts/              # Project and research articles
├── publications/       # Academic papers
└── about.md           # About page
```

## Features

- **Math support** - Use LaTeX for equations (enabled globally)
- **Code highlighting** - Syntax highlighting for code blocks
- **Dark/light mode** - Auto-adapts to system preferences
- **Tags** - Organize posts with tags in front matter

## Theme Documentation

For advanced features and customization, see the [Typo theme wiki](https://tomfran.github.io/typo-wiki/).
