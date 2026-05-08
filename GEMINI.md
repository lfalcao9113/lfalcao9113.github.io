# Academic Pages - Lucas Falcão Portfolio

This project is a personal academic portfolio website based on the [Academic Pages](https://academicpages.github.io/) template, which is a fork of the [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) Jekyll theme. It is designed to showcase research, publications, talks, and teaching.

## Project Overview

- **Static Site Generator:** Jekyll (Ruby)
- **Theme:** Minimal Mistakes (Academic Pages fork)
- **Main Technologies:** Ruby, Sass/SCSS, JavaScript, Python (for content automation), Docker
- **Hosting:** GitHub Pages

## Building and Running

### Local Development (Ruby installed)
1. Install dependencies:
   ```bash
   bundle install
   ```
2. Serve the site locally:
   ```bash
   bundle exec jekyll serve -l -H localhost
   ```
   The site will be available at `http://localhost:4000`.

### Docker
1. Ensure Docker and Docker Compose are installed.
2. Run the site:
   ```bash
   docker compose up
   ```

### JavaScript Assets
If you modify JS files in `assets/js/`, rebuild the minified bundle:
```bash
npm run build:js
```

## Content Management

The site uses Jekyll Collections to manage different types of academic content.

### Collections
- **Publications:** Found in `_publications/`. Can be generated from BibTeX or TSV using scripts in `markdown_generator/`.
- **Talks:** Found in `_talks/`. Can be generated from TSV using scripts in `markdown_generator/`.
- **Teaching:** Found in `_teaching/`.
- **Portfolio:** Found in `_portfolio/`.
- **Blog Posts:** Found in `_posts/`.
- **Talk Map:** An interactive map of talk locations, located in `talkmap/`. It is typically updated by the `talkmap.py` script in the root directory.

### Automation Scripts (`markdown_generator/`)
Use these Python scripts to automate the creation of markdown files for publications and talks:
- `publications.py`: Generates publication pages from `publications.tsv`.
- `pubsFromBib.py`: Generates publication pages from a BibTeX file.
- `talks.py`: Generates talk pages from `talks.tsv`.

### CV Generation
- `scripts/cv_markdown_to_json.py`: A script likely used to convert markdown CV data to JSON format.
- `scripts/update_cv_json.sh`: Shell script to trigger CV updates.

## Configuration

- `_config.yml`: Main site configuration (title, author info, collections, plugins).
- `_data/navigation.yml`: Defines the header navigation menu.
- `_data/authors.yml`: Detailed author information.
- `_sass/`: SCSS files for styling. `_sass/_themes.scss` and `_sass/theme/` contain theme-specific styles.

## Development Conventions

- **Content:** Use Markdown for all content files in collections and `_pages/`.
- **Front Matter:** Ensure every page and collection item has appropriate YAML front matter (e.g., `title`, `collection`, `permalink`, `date`).
- **Assets:** Place PDFs and other downloadable files in the `files/` directory. Images should go in `images/`.
- **Styling:** Adhere to the Minimal Mistakes SCSS structure. Avoid inline styles; use the theme's helper classes or add to `_sass/`.
