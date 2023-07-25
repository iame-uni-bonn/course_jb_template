# Template for Flipped Classroom Courses Using Jupyter Book

[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/hmgaudecker/finanz_und_sozialpolitik/main.svg)](https://results.pre-commit.ci/latest/github/hmgaudecker/finanz_und_sozialpolitik/main)
[![image](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)



## Purpose

This is a template repository for flipped classroom courses. It uses [jupyter book](https://jupyterbook.org/en/stable/intro.html) to create an online textbook with course materials built from markdown files and jupyter notebooks. It allows to launch notebooks on JupyterHub. 

## Usage

### Replace Placeholders
Find and replace the following placeholders in the entire directory.

| Placeholder          | Replacement Example                                          |
| -------------------- | ------------------------------------------------------------ |
| `COURSE_SLUG`        | `applied_micro`                                              |
| `COURSE_NAME`        | `Applied Microeconomics`                                     |
| `COURSE_DESCRIPTION` | `Ph.D. / M.Sc. course in Applied Microeconomics, Summer Term 2023` |
| `COURSE_URL`         | `https://www.wiwi.uni-bonn.de/gaudecker/_static/applied_micro/landing-page.html` (course website, not git repository) |
| `TEACHER_NAMES`      | `Prof. Dr. Hans-Martin von Gaudecker and Florian Zimmermann` |
| `COURSE_YEAR`        | `2023`                                                       |

Find and replace https://github.com/iame-uni-bonn/course_jb_template with the course's git repo URL in the entire directory. (This should be multiple entries in `setup.cfg` and in `./src/COURSE_SLUG/_config.yml`.)

Rename `./src/COURSE_SLUG`.

### Requirements

Create and activate the environment with

```console
$ conda/mamba env create
$ conda activate COURSE_SLUG
$ npm install
```

### Build Project

To build the project, type

```console
$ pytask
```

### View Materials

To view the jupyter books with course materials, open
- `./student_book/index.html` (student version) or
- `./teacher_book/index.html` (teacher version) in a browser.

To view the screencast slides in the interactive version, run

```console
$ npx slidev book_source/teachers/[chapter]/screencast_[x]/slides.md
```

### Add New Chapters

1. Copy and paste `./scr/applied_microeconomics/chapter_template`, and rename according
   to `CHAPTER_NAMES` in `src/applied_microeconomics/config.py`.
1. Append the folder name to CHAPTER_NAMES in
   `./src/COURSE_SLUG/config.py`.
1. Run `pytask` to build the book and work on the To-Do list that is shown on the
   landing page when opening the book.
1. Remove finished To-Dos from the list by deleting them in
   `./src/COURSE_SLUG/[chapter]/contents.md`.

### Add New To-Dos

You can add additional To-Dos in .md files as well as in markdown cells in .ipynb files. For instance, add the following line to a markdown file:

````
```{todo}
A description of what needs to be done.
```
````

To-Dos will only show up in the teacher book. 

## Credits

This project was created with [cookiecutter](https://github.com/audreyr/cookiecutter)
and the
[econ-project-templates](https://github.com/OpenSourceEconomics/econ-project-templates).
