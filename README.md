# Volodymyr's Personal Website

A personal website built with Jekyll showcasing projects, blog posts, and interests.

> Formerly known as "Losing my sanity over developing semi-functional website by Vibe-coding..."

## Project Structure

```
my-website/
├── _config.yml         # Site configuration
├── _includes/          # Reusable components
├── _layouts/           # Page templates
├── _posts/             # Blog posts
├── _projects/          # Project collection
├── assets/             # Static files (CSS, images)
├── index.md            # Homepage
├── about.md            # About page
├── blog.md             # Blog listing page
├── projects.md         # Projects listing page
└── README.md           # This file
```

## Local Development

### Prerequisites

- Ruby version 2.5.0 or higher
- RubyGems
- GCC and Make

### Setup

1. Install Jekyll and Bundler:
   ```
   gem install jekyll bundler
   ```

2. Install dependencies:
   ```
   bundle install
   ```

3. Run the local server:
   ```
   bundle exec jekyll serve
   ```

4. View the site at `http://localhost:4000`

## Customization

- Edit `_config.yml` to update site metadata
- Modify layouts in `_layouts/` to change page structure
- Update CSS in `assets/css/custom.css`
- Add new projects in `_projects/`
- Create new blog posts in `_posts/`

## Deployment

This site is designed to be deployed to GitHub Pages:

1. Create a GitHub repository (username.github.io)
2. Push this code to the repository
3. Enable GitHub Pages in the repository settings

## License

See the LICENSE file for details.
