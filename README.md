# Personal Page (Jekyll Version)

This repository contains my personal website, powered by the [Jekyll](https://jekyllrb.com) static site generator. 

## Project Structure
- `_posts/` — Put the blog posts here (use `YYYY-MM-DD-title.md` format).
- `_layouts/` — Templates for pages and posts.
- `_site/` — The generated website (do not edit these files directly).
- `_config.yml` — Global settings for the site.
- `Gemfile` — Manages Ruby dependencies (Jekyll, plugins).

## Local Development

Since moving to Jekyll, we use **Bundler** instead of Python's simple server. This ensures all plugins (like SEO tags and feeds) are compiled correctly before viewing.

### Prerequisites
- **Ruby 3.4+** (Installed via [Homebrew](https://brew.sh))
- **Bundler & Jekyll** (`gem install jekyll bundler`)

### How to Run Locally
1. **Navigate to the project folder:**

2. **Install/Update dependencies:**
(Only needed if the Gemfile changes)
```bash 
bundle install
```

3. **Start the Jekyll server:**
```bash
bundle exec jekyll serve --baseurl ""
```

4. **View the site:**
Open http://localhost:4000 in your browser. The server will automatically refresh whenever you save a file.


## Writing Blogs
1. Create a new .md file in the _posts/ directory.
2. Ensure it has "Front Matter" at the top:
```yaml
---
layout: post
title: "My New Blog Post"
date: 2024-05-20
---
```

3. Save the file; Jekyll will detect the change and update the local site immediately.

Author: Manas Tripathi