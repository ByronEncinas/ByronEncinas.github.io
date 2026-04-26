# Byron Encinas Blog

This is a simple Jekyll-based blog hosted on GitHub Pages.

## How to Add Blog Posts

1. Create a new file in the `_posts` directory.

2. Name the file in the format: `YYYY-MM-DD-title-of-post.md`
   - YYYY: Year (e.g., 2026)
   - MM: Month (01-12)
   - DD: Day (01-31)
   - title-of-post: A URL-friendly title with hyphens instead of spaces

3. Add front matter at the top of the file:

   ```
   ---
   layout: default
   title: "Your Post Title"
   date: YYYY-MM-DD
   ---
   ```

4. Write your blog post content in Markdown below the front matter.

5. Commit and push the changes to the `main` branch. GitHub Pages will automatically build and publish your site.

### Example

Create `_posts/2026-04-26-my-first-post.md`:

```
---
layout: default
title: "My First Post"
date: 2026-04-26
---

# Hello World

This is my first blog post!
```

Your post will be available at `https://byronencinas.github.io/2026/04/26/my-first-post/`

## Local Development

To preview your site locally, install Jekyll and run:

```bash
jekyll serve
```

Then visit `http://localhost:4000`.
