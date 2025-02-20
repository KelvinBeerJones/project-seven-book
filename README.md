# project-seven-book

This project creates a Jupyter Book from multiple Jupyter Notebooks and created a website hosted on GitHub Pages.


## pip install

`pip install -U jupyter-book pyppeteer ghp-import`

## Create a Jupyter Book

`jupyter-book create ~/Desktop/project-seven-book`

This will generate a JB structure

## Customise Jupyter Book files

- customised _config.yml
    - title
    - author
    - logo.png to logo.jpg
    - repository:
        - set url to https://github.com/KelvinBeerJones/project-seven-book
        - remove path_to_book
    - use_issues_button: false
- customised _toc.yml
- customised intro.md
- added 'chapters' dir with .ipynb files from GitHub Publish repo
- added 'images' dir with all image files used in Notebooks
- deleted:
    - bibliography file
    - markdown-notebooks.md
    - markdown.md
    - notebooks.ipynb
    - logo.png (replaced with logo.jpg of the UoB logo)


## Build Jupyter Book

Run: `jupyter-book build ~/Desktop/project-seven-book --builder singlehtml`

You could also build multi-page site with `jupyter-book build ~/Desktop/project-seven-book` or with a PDF like `jupyter-book build ~/Desktop/project-seven-book --builder pdfhtml`

Using the built in PDF misses images and ignores page numbers, so instead just open HTML webpage in Chrome and print PDF from there/


## GitHub Pages

- Setup initial GitHub repo:
    - create GitHub repo project-seven-book
    - clone: e.g. git clone https://github.com/KelvinBeerJones/project-seven-book.git
    - copy all contents within book folder into repo: cp -r kelvin-book/* kelvin
    - commit and push to GitHub
    - create new branch on GitHub called gh-pages
    - on GH go to Settings > Pages and set branch to gh-pages
- Use ghp-import to publish a GitHub Pages version to the gh-pages branch:
    - single page (use this): `ghp-import -n -p -f _build/singlehtml`
    - multipage: `ghp-import -n -p -f _build/html`
- Copy images into root dir on gh-pages branch:
    - (on main branch) `cp -r ~/Desktop/project-seven-book/images/ ~/Desktop/project-seven-book-images/`
    - `git checkout gh-pages`
    - `cp ~/Desktop/project-seven-book-images/*.png ~/Desktop/project-seven-book`
    - git: add, commit, and push the gh-pages branch

