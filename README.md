# README.md sipbs-compbiol-book-template

This repository is a template, intended as a convenience to take some manual work out of setting the style for Quarto books used by SIPBS Computational Biology.

This version of the template includes:

- a GitHub Action (`.github/workflows/publish.yml`) that should update the GitHub Pages version of the book on each push to the `main` branch.
- an example WebR page

## How to use this template

### Setting Up

1. Click on the `Use This Template` button to create a new repository/project based on this template
2. Make your new repository [public](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/setting-repository-visibility)
3. Set your pages site to [render from the `gh-pages` branch](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)
4. Clone or download the project to your local development environment
5. Rename the `sipbs-compbiol-book-template.Rproj` file to suit your new repository's name
6. Open the project folder and modify `_variables.yml` to change:
  - `[A]` academic year
  - `[B]` administrator name and contact information
  - `[C]` GitHub URLs for the repository
4. Modify `_quarto.yml` to change:
  - `[A]` book title
  - `[B]` footer text
  - `[C]` GitHub repository URL
  - `[D]` author name and publication/presentation date
  - `[E]` chapters and sections
5. Modify `DESCRIPTION` to change:
  - `[A]` package name and book title
  - `[B]` author names and emails
  - `[C]` repository URL
  - `[D]` required R packages
  - `[E]` licensing information
6. Change or update the licence, if required
7. Add the `quarto-webr` extension (if necessary) using the command `quarto add coatless/quarto-webr`
8. Add the `custom-callout` extension (if necessary) using the command `quarto add coatless-quarto/custom-callout`
9. Generate the book by issuing `quarto render` in the terminal, or using the `Render` button in `RStudio`
10. Commit your updates in the local development environment
11. Publish your book to GitHub Pages by issuing `quarto publish gh-pages` in the terminal
12. When the pages have built on GitHub Pages, click on the `About` settings (the cog icon) to modify the page description and select `Use your GitHub Pages website`, to have the GitHub Pages site linked from the repository

### General Usage

1. Make changes to the `.qmd` files, updating chapter information in `_quarto.yml` and `R` package information in `DESCRIPTION`, as needed for your material
2. Commit your changes locally to the git repository
3. Push your changes to the GitHub repository

### Using `WebR`

[`WebR`](https://github.com/coatless/quarto-webr) provides a sandboxed version of `R` that runs in the browser. This enables us to write workshops that ask students to use `R` "live" without requiring an installation on their machine, thereby increasing accessibility and avoiding some technical issues.

Being sandboxed, `WebR` has no interaction with the local filesystem, and there are limitations on the libraries that can be installed. There is no quick route around the library limitations, but we can provide example files for students to work with on their machines.

#### Providing data for `WebR` exercises

We need to make the datasets available in the workshop repository, and preload them on the exercise Quarto page in a `webr-r` cell with the `setup` context. An example can be seen at [https://github.com/sipbs-compbiol/BM214-Workshop-3/blob/main/exercise-03_reporter.qmd](https://github.com/sipbs-compbiol/BM214-Workshop-3/blob/main/exercise-03_reporter.qmd) where the `reporter_curves.csv` file is downloaded in the first `webr-r` cell.

There is also an example in the `webr-example.qmd` `WebR` playground page, in this repository template.
