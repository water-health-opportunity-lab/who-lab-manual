# WHO Lab Manual

This repository contains the **Water, Health, Opportunity (WHO) Lab Manual** at the George Washington University. It documents lab onboarding, practices, policies, and resources for new and current lab members.

This manual was created with inspiration from other scientists' [lab manuals](https://jadebc.github.io/lab-manual/) and [policies](https://github.com/pzivich/LabGroupMaterials/tree/main). Contributors thus far include Xindi (Cindy) Hu and Jahred Liddie.

The manual is built with **Bookdown (R Markdown)**. You can run it locally, edit content, and render an updated version of the manual.

------------------------------------------------------------------------

## 📦 Getting Started

### 1. Clone the repository

``` bash
git clone https://github.com/YOUR-USERNAME/who-lab-manual.git
cd who-lab-manual
```

### 2. Open in RStudio

Double-click the .Rproj file (who-lab-manual.Rproj) to open the project in RStudio. Alternatively, open R in the project folder.

### 3. Running the Manual Locally (Bookdown)

Install R packages (first time only):

``` bash
install.packages(c("bookdown", "rmarkdown"))
```

Build and preview the manual:

``` bash
bookdown::serve_book()
```

This will open a local preview in your browser. The manual updates automatically whenever you save a file.

### 4. Editing Content

Chapters are written in .Rmd (R Markdown) files.

Because `_bookdown.yml` does not list rmd_files, Bookdown builds chapters in this order:

- index.Rmd (must exist, becomes the Welcome page)

- All other .Rmd files in alphanumeric order

To add a new chapter

Create a new `.Rmd` file (e.g., `17-datasets.Rmd`).

Save it in the repo root.

Give it a numeric prefix so it appears in the desired order.

Run `bookdown::serve_book()` again to preview.

### 5. Publishing Updates

When you're ready to publish changes: By default, the rendered HTML is saved to the docs/ folder (set in \_bookdown.yml).

#### Build locally

From R/RStudio Console:

``` r
bookdown::render_book("index.Rmd")
```

This regenerates the HTML files into the docs/ directory (as set in \_bookdown.yml).

#### Commit the build

Make sure `docs/` is committed and pushed to GitHub (do not add it to .gitignore). Also ensure there is a `.nojekyll` file in `docs/` to disable Jekyll:

``` bash
touch docs/.nojekyll
git add docs
git commit -m "Update manual"
git push
```

#### Host the manual on GitHub Pages:

- Go to your repo → Settings → Pages.

- Under Source, choose Deploy from a branch.

- Select branch: `main`, folder: `/docs`.

- Save.

Your manual will be published at <https://water-health-opportunity-lab.github.io/who-lab-manual/>.
