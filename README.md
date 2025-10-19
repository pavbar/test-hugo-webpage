# Hugo Quickstart

This project uses [Hugo](https://gohugo.io/), a fast static site generator. The steps below cover the basics so you can preview and publish the site.

## Prerequisites
- Install the latest **Hugo Extended** release for your platform. Verify with:
  ```bash
  hugo version
  ```
- Optional but useful: install Git to version-control content updates.

## Local Development
1. Start the built-in server:
   ```bash
   hugo server
   ```
2. Open the URL shown in the terminal (default: http://localhost:1313/) to preview changes live.
3. Stop the server with `Ctrl+C` when you are finished.

## Creating Content
- Generate a new page or post with:
  ```bash
  hugo new posts/my-first-post.md
  ```
- Edit the generated Markdown file under `content/` to add your text and front matter.

## Building for Production
- Create the static site output:
  ```bash
  hugo
  ```
- Hugo writes the compiled site to the `public/` directory. Deploy the contents of `public/` to your hosting provider or static hosting service.

## Customizing the Site
- Global settings (title, theme, params) live in `hugo.toml`.
- Static assets such as images and custom styles go in `static/` or `assets/`.
- Layout overrides reside in `layouts/`. Anything placed here takes precedence over the theme defaults.

For deeper guidance, refer to the [official Hugo documentation](https://gohugo.io/documentation/).
