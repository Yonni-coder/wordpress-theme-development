# WordPress Theme Development

Learning and experimenting with custom WordPress theme development, including templates, hooks, and best practices.

**Status**: Personal project / experimentation lab

**Overview**

- **Goal**: collect experiments and example themes to demonstrate template structure, hooks (actions & filters), and WordPress development best practices.
- **Contents**: a full WordPress codebase for a local environment plus a `wp-content` directory where themes and plugins can be developed.

**Highlights**

- Example theme templates.
- Demonstrations of hooks (actions and filters).
- Local development workflows (Docker / `docker-compose`).

**Important locations**

- `wp-content/themes/`: place to create or drop custom themes.
- `wp-content/plugins/`: test or utility plugins.
- WordPress core files in the repository root and `wp-admin`, `wp-includes` for a complete local environment.
- `docker-compose.yml`: optional local environment configuration (if present).

**Quick local setup**

1. Clone the repository:

```bash
git clone https://github.com/Yonni-coder/wordpress-theme-development.git
cd wordpress-theme-development
```

2. If a valid `docker-compose.yml` is present, start the containers:

```bash
docker-compose up -d
```

3. Open the local WordPress site (check `docker-compose.yml` for the configured port) and enable a theme from the WordPress admin.

Note: If you are not using Docker, place this folder in your local PHP/MySQL server root (for example `htdocs` for XAMPP) and configure `wp-config.php` with your database credentials.

**Create a quick theme**

1. Create a theme folder:

```bash
mkdir -p wp-content/themes/my-theme
```

2. Add at minimum a `style.css` (theme header) and an `index.php` file.

Example `wp-content/themes/my-theme/style.css` header:

```css
/*
Theme Name: My Theme
Author: Your Name
Version: 0.1
*/
```

3. Activate the theme from the WordPress admin (`Appearance > Themes`).

**Development tips**

- Enable debugging in `wp-config.php` while developing:

```php
define( 'WP_DEBUG', true );
define( 'WP_DEBUG_LOG', true );
define( 'WP_DEBUG_DISPLAY', false );
```

- Follow WordPress coding standards (use PHPDoc, escape outputs, validate data).
- Use `get_template_part()` to reuse template fragments.
- Prefer hooks (actions/filters) to extend behavior without modifying core files.

**Recommended tools**

- Node.js + npm or Yarn for building assets (Sass, PostCSS, bundlers).
- Browsersync or LiveReload for automatic reloads.
- WP-CLI for common tasks (user creation, imports/exports, plugin/theme activation).

Useful example commands:

```bash
# List installed plugins with WP-CLI (if WP-CLI is installed)
wp plugin list

# Example asset build
npm install
npm run build
```

**Contributing / Next steps**

- Add example themes into `wp-content/themes/` with their own `README.md` files.
- Document common templates (`header.php`, `index.php`, `single.php`, `page.php`, `archive.php`, `functions.php`).
- Add hook examples in `mu-plugins/` or small test plugins.

**Resources**

- Official WordPress developer docs: https://developer.wordpress.org/
- Themes: https://developer.wordpress.org/themes/

**License**
This repository may include WordPress core files (GPL). New themes or files you add should use GPL or another compatible license of your choosing.

---

This file was created for the `wordpress-theme-development` repository as an entrypoint for developers experimenting with WordPress theme development.
