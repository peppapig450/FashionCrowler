# Web Scraper for Fashion Marketplace Sites

A Python tool for scraping multiple shopping websites such as Grailed, Depop, GOAT, and STOCKx (maybe more).

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)


## Introduction

This project aims to provide a convenient and unified interface for scraping product listings and related data from various online shopping platforms.

This originated from my AP Computer Science Principles project which was just a Grailed scraper, and I wished to expand it to more sites so I created this.
The original is [here](https://github.com/peppapig450/final-create-task-scraping).


## Project Plan

#### To-Do List / Possible Features (By Priority)

- [ ] Implement logging

- ~~[X] Implement Depop data extraction and scraping.~~

- [ ] Implement Stockx data extraction and scraping.

- [X] Figure out how we're gonna handle the respective scrapers. [Line 10](https://github.com/peppapig450/FashionCrawler/blob/main/main.py#L10)

- [ ] Instead of scraping Stockx for market data use their api. (maybe use go for speed)

- [ ] Options to filter the dataframe by a category

- [ ] Headless mode doesn't work if it can't be fixed -> maybe try minimized mode?

## Installation

Install using [Poetry](https://python-poetry.org/) (recommended):

```bash
# clone repository
git clone https://github.com/peppapig450/FashionCrawler

# switch to directory
cd FashionCrawler

# install dependencies
poetry install
```

Install using a virtual environment

```bash
# clone repository
git clone https://github.com/peppapig450/FashionCrawler

# switch to directory
cd fashioncrawler

# setup and activate virtual environment
python3 -m venv venv && source venv/bin/activate

# install dependencies
pip install -r requirements.txt
```

## Usage
Fashion Crawler is a web scraper for various fashion marketplace sites. Below are the available options for running the scraper.

### Options:

#### Site Selection:
 - By default, all supported sites are enabled, or it uses the sites specified in the `config.yaml` file.
 - `--enabled-site ENABLE_SITE`: Enable specific site(s) by providing a comma-seperated list of supported site names.
 - `--disabled-site DISABLE_SITE`: Disable specific site(s) by providing a comma-seperated list of supporte site names.

#### Search Options:
- `-s SEARCH`, `--search SEARCH`: Specify a search query to scrape for.

#### Output Options:
- If no output option is specified, the scraper prints the result as a table on the command line.
- `-j`, `--json`: Output the result as JSON.
- `-c`, `--csv`: Output the result as CSV.
- `-y`, `--yaml`: Output the result as YAML.
- `-o OUTPUT`, `--output OUTPUT`: Specify the output file name (without extension).
- `--output-dir OUTPUT_DIR`: Specify the output directory.

### Example Usage:

To enable only Grailed and Depop sites, search for "Nike Air Force", and output the result as JSON to a file named "output.json" in the "data" directory, the command would be:

```bash
poetry run python main.py --enable-site Grailed,Depop --search "Nike Air Force" -j -o output --output-dir data
```