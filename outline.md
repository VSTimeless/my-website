# Outline for Developing Volodymyr's Personal Website

## 1. Project Setup
This section covers the initial setup to get the website development environment ready and prepare it for GitHub Pages hosting.

- **Install Prerequisites**:
  - Install Ruby (Jekyll requires Ruby; download from [ruby-lang.org](https://www.ruby-lang.org/)).
  - Install Jekyll: Run `gem install jekyll bundler` in your terminal.
- **Create a New Jekyll Site**:
  - Run `jekyll new volodymyr-site` to generate a new Jekyll project.
  - Navigate into the directory: `cd volodymyr-site`.
- **Initialize Git Repository**:
  - Run `git init` to start a Git repository.
  - Create a `.gitignore` file with `node_modules/` and `_site/` to exclude unnecessary files.
  - Commit initial files: `git add . && git commit -m "Initial commit"`.
- **Set Up GitHub Pages**:
  - Create a new repository on GitHub (e.g., `volodymyr.github.io` or `username.github.io`).
  - Link local repo to GitHub: `git remote add origin <repository-url>`.
  - Push to GitHub: `git push -u origin main`.

## 2. Theme Selection
Choose a Jekyll theme that aligns with the minimal, responsive design of the Cursor blog page.

- **Research Themes**:
  - Look for free, minimal, and responsive Jekyll themes. Options include:
    - **Minima**: Default Jekyll theme, simple and clean.
    - **Lanyon**: Minimal with a sidebar option.
    - **Hyde**: Sleek and responsive.
  - Preview themes at [jekyll-themes.com](https://jekyll-themes.com/) or GitHub repositories.
- **Select and Install Theme**:
  - Choose a theme (e.g., Minima for simplicity).
  - Edit `Gemfile` to include the theme: `gem "minima", "~> 2.5"`.
  - Update `_config.yml`: Set `theme: minima`.
  - Install dependencies: `bundle install`.

## 3. Customization
Customize the theme to create a structure that reflects Volodymyr’s identity and interests, keeping it modular with reusable components.

- **Homepage (`index.md` or `index.html`)**:
  - **Hero Section**:
    - Large text: "Volodymyr [Last Name]".
    - Tagline: "Electrical Engineering Student | Tech Enthusiast".
    - Optional: Add a small profile photo (compressed JPEG, ~100KB).
  - **About Section**:
    - Content: "I’m a [year] year EE student at [University]. I’m passionate about building circuits in my home lab, reading books on technology and science, listening to podcasts like [example], staying active at the gym, and capturing the world through photography."
  - **Featured Projects**:
    - Display 2–3 highlighted projects in a grid or list.
    - Each project includes: Title, 1–2 sentence description, small image (e.g., 300x200px, compressed).
    - Link to full Projects page.
  - **Recent Blog Posts**:
    - List 3–5 latest posts with title, date, and 1-sentence excerpt.
    - Link to full Blog page.
  - **Contact Section**:
    - Simple text: "Get in touch: [volodymyr@email.com](mailto:volodymyr@email.com)".
- **Navigation**:
  - Edit `_includes/header.html` or theme’s navigation file.
  - Add links: Home (`/`), Projects (`/projects/`), Blog (`/blog/`), About (`/about/`).
  - Ensure navigation is in header, styled cleanly like Cursor’s top bar.
- **Projects Page (`projects.md`)**:
  - Create a `_projects` directory for Jekyll collections.
  - Add to `_config.yml`:
    ```yaml
    collections:
      projects:
        output: true
        permalink: /projects/:title/
    ```
  - Create project files (e.g., `_projects/homelab-circuit.md`) with:
    ```yaml
    ---
    title: "Home Lab Circuit"
    description: "A custom power supply built for my home lab."
    image: "/assets/images/circuit.jpg"
    ---
    ```
  - Build `projects.md` to loop through projects:
    ```markdown
    ---
    layout: page
    title: Projects
    permalink: /projects/
    ---
    {% for project in site.projects %}
      - [{{ project.title }}]({{ project.url }}) - {{ project.description }}
    {% endfor %}
    ```
- **Blog**:
  - Use Jekyll’s built-in blogging system.
  - Create posts in `_posts/` (e.g., `2023-10-01-welcome.md`):
    ```markdown
    ---
    layout: post
    title: "Welcome to My Site"
    date: 2023-10-01
    ---
    This is my first post about my EE journey and interests!
    ```
  - Edit `blog.md` to list posts:
    ```markdown
    ---
    layout: page
    title: Blog
    permalink: /blog/
    ---
    {% for post in site.posts %}
      - [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%Y-%m-%d" }}
    {% endfor %}
    ```
- **About Page (`about.md`)**:
  - Optional if homepage About section is sufficient.
  - Content: Expand on bio, interests, and EE goals.
  - Example:
    ```markdown
    ---
    layout: page
    title: About
    permalink: /about/
    ---
    I’m Volodymyr, an EE student exploring circuits, literature, and more.
    ```
- **Interests Integration**:
  - Mention in About section: "My interests include books, podcasts, home lab, gym, and photography."
  - Write blog posts for each (e.g., "Top 5 Tech Podcasts I Recommend", "My Home Lab Setup").
  - Optional: Add a small "Interests" section on homepage with icons and brief text (e.g., "Photography: Capturing moments since 2020").
- **Data Files** (for modularity):
  - Create `_data/interests.yml`:
    ```yaml
    - name: Books
      description: "Currently reading: [Book Title]"
    - name: Podcasts
      description: "Favorite: [Podcast Name]"
    ```
  - Display on homepage with Liquid:
    ```markdown
    {% for interest in site.data.interests %}
      - **{{ interest.name }}**: {{ interest.description }}
    {% endfor %}
    ```

## 4. Content Creation
Populate the site with Volodymyr’s specific details and interests.

- **About Section**:
  - Finalize bio with university, year, and personal touch.
- **Projects**:
  - Add 3–5 EE projects (e.g., "LED Matrix Display", "Home Lab Power Supply").
  - Include title, description, and image for each.
- **Blog Posts**:
  - Write 2–3 initial posts:
    - "Why I Built a Home Lab"
    - "My Favorite Photography Tips"
    - "Books That Inspire My EE Studies"
- **Contact**:
  - Use a real email or placeholder: `[volodymyr@example.com](mailto:volodymyr@example.com)`.

## 5. Optimization
Ensure the site is fast and responsive, mirroring the Cursor blog’s performance.

- **Responsiveness**:
  - Test theme on desktop, tablet, and mobile using browser tools.
  - Adjust CSS if needed (e.g., `@media` queries in `assets/css/custom.css`).
- **Image Optimization**:
  - Compress images to <100KB using tools like [TinyPNG](https://tinypng.com/).
  - Use JPEG for photos, PNG for graphics.
  - Add alt text: `<img src="/assets/images/photo.jpg" alt="Home lab circuit">`.
- **Asset Minification**:
  - Minify custom CSS/JavaScript using [Minifier.org](https://www.minifier.org/) if theme doesn’t handle it.

## 6. Additional Features
Enhance the site with useful extras while keeping it minimal.

- **Social Media Links**:
  - Add to footer (`_includes/footer.html`):
    ```html
    <a href="https://github.com/volodymyr">GitHub</a> | <a href="https://twitter.com/volodymyr">Twitter</a>
    ```
- **SEO**:
  - Add Jekyll SEO Tag plugin to `Gemfile`: `gem "jekyll-seo-tag"`.
  - Update `_config.yml`:
    ```yaml
    plugins:
      - jekyll-seo-tag
    ```
  - Add meta tags in layout (`_layouts/default.html`): `{% seo %}`.
- **Accessibility**:
  - Use semantic HTML (e.g., `<nav>`, `<main>`).
  - Ensure color contrast (e.g., dark text on light background).
  - Test with a tool like [WAVE](https://wave.webaim.org/).

## 7. Testing and Deployment
Verify the site works locally and deploys correctly to GitHub Pages.

- **Local Testing**:
  - Run `bundle exec jekyll serve`.
  - Open `http://localhost:4000` in browser.
  - Check links, layout, and responsiveness.
- **Fix Issues**:
  - Debug broken links or styling errors.
- **Deploy**:
  - Commit changes: `git add . && git commit -m "Site ready"`.
  - Push to GitHub: `git push origin main`.
  - Verify at `https://username.github.io`.
- **Store Outline**:
  - Create `outline.md` with this content in the repository root.
  - Commit and push for reference.

## 8. Maintenance
Keep the site updated over time.

- **Blog Updates**:
  - Add new posts monthly about projects or interests.
- **Project Additions**:
  - Update `_projects/` with new EE work.
- **Content Refresh**:
  - Revise About section or interests as they evolve.

