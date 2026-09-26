
# Nanxuan Li's Data Science Website

This is my personal website built using Quarto. It contains my background information and blog posts, including data analysis using Python and R.

## 1. Requirements

Install the following software before building the website:

- Git
- Quarto (version: 1.10.18)
- uv 0.12.5
- Python 3.14 (managed by uv)
- R 4.6.1

The Python environment is managed by uv, and the R environment is managed by renv.

## 2. Clone the Repository

Open Git Bash and run:

```bash
git clone https://github.com/Nei112/nei112.github.io.git
cd nei112.github.io
```

All the following commands should be run from the root directory of this repository.

## 3. Restore the Python Environment

Run:

```bash
uv sync
```

This installs the Python version and packages specified by `.python-version`, `pyproject.toml` and `uv.lock`.

## 4. Restore the R Environment

Run:

```bash
Rscript -e 'renv::restore(prompt = FALSE)'
```

This restores the R packages recorded in `renv.lock`. The project automatically activates renv through `.Rprofile`.

## 5. Build the Website

On Windows, using Git Bash, run:

```bash
export QUARTO_PYTHON="$(pwd)/.venv/Scripts/python.exe"
quarto render
```

These commands use the project's Python environment and generate the entire Quarto website, including the Python and R blog posts.

The generated website is saved in the `docs/` directory.

To view the website locally, open `docs/index.html` in a web browser.

## 6. Data Source

Both computational blog posts use the Palmer Penguins dataset.

Data source: [Palmer Penguins](https://allisonhorst.github.io/palmerpenguins/), Palmer Station Antarctica LTER.

The data is included in the Python and R packages used by this project. The packages require an internet connection during their initial installation, but the analysis does not download the dataset separately.
