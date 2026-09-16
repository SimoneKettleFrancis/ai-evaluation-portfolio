# Keeping this portfolio up to date

The website is the visitor-facing portfolio. This repository holds the text and pictures behind it. You can update the content directly in your browser.

## The everyday workflow

**Write a study → preview the change → save it → let GitHub Pages rebuild.**

The website is updated after a saved change is built and deployed; it does not publish each keystroke. GitHub notes that publication can take up to 10 minutes.

## Update an existing example

1. Open [`docs/studies/`](docs/studies/) and choose a file.
2. Select the pencil button to edit it.
3. Change the text below the small settings block at the top. Use **Preview** to check headings, images, and tables.
4. Select **Commit changes**, add a short description such as “Clarify evaluation reasoning,” and save to `main`.
5. After the Pages deployment finishes in **Actions**, refresh the portfolio website.

Saving to `main` publishes the revised content. Use a separate branch and a pull request if you want a review before publication. This is a public repository, so a branch is not a private draft space.

## Add a new study

1. Open [`templates/case-study.md`](templates/case-study.md), view the raw text, and copy it.
2. In [`docs/studies/`](docs/studies/), select **Add file → Create new file**.
3. Use a descriptive filename such as `source-verification.md` and paste the template.
4. Replace the title, category, summary, and study text. Set `number` to the next two-digit number, such as `"07"`.
5. Keep `layout: case`. This makes the website recognize it as a gallery entry.
6. Preview and commit the file. The website gallery will include it automatically after the next successful build.

The template reuses an existing generic workflow image so it works immediately. Replace that image with an original visual when ready. The Markdown case file is also readable directly on GitHub.

## Add or replace a picture

1. Create a new diagram, screenshot of your own synthetic example, or image you have permission to use.
2. Upload it with **Add file → Upload files** inside [`docs/assets/`](docs/assets/).
3. In the study's top settings, use `image: "/assets/your-picture.png"` and write a useful `image_alt` description. This controls the website gallery picture.
4. In the study body, use `![Description of the picture](../assets/your-picture.png)`. This shows it within the study and on GitHub.

Landscape pictures around a 1.9:1 ratio fit the gallery well. SVG, PNG, or JPG images can be used. The included SVG diagrams are editable text files.

## Feature the study on the repository homepage

The website gallery updates automatically. The README gallery is curated separately. Add a plain link to the new study, or copy an existing gallery cell and update its title, image, description, and destination.

## Content boundaries

- Keep the public portfolio separate from private work records.
- Use original or explicitly shareable examples. Recreate training screenshots with synthetic content instead of uploading the originals.
- Leave internal names, task IDs, private links, account details, and employer-specific scoring instructions out of public commits.
- Label demonstrations clearly. Only describe actual measured results when their evidence and publication rights are established.
- Deleting text later does not erase it from Git history. Do the content review before committing.

## Website configuration

The site uses GitHub's built-in Jekyll support. Under **Settings → Pages**, choose **Deploy from a branch**, branch **main**, folder **/docs**. No paid theme, database, analytics service, or custom domain is required.

To rename the repository later, also update `baseurl` in `docs/_config.yml` and the repository/website links. To change colors or spacing, edit `docs/assets/style.css`.

## Documentation

- [Edit files in GitHub](https://docs.github.com/en/repositories/working-with-files/managing-files/editing-files)
- [GitHub Markdown and pictures](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- [Configure GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [GitHub Pages publishing timing](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll)
