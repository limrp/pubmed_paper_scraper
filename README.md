# PubMed Scraper

This repository contains a Python script that scrapes search results from the NCBI website, extracting titles, links, publication years, journals, and DOIs. The results are then saved into a CSV file.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Examples](#examples)
- [Dependencies](#dependencies)
- [Contributing](#contributing)
- [License](#license)

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/limrp/pubmed_scraper.git
cd pubmed_scraper
```

### 2. Create a Virtual Environment (optional but recommended)

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install the Required Libraries

Install the necessary Python libraries using `pip`:

```bash
pip install -r requirements.txt
```

Alternatively, you can install the required libraries individually:

```bash
pip install selenium beautifulsoup4 pandas argparse
```

### 4. Install ChromeDriver

Make sure you have [ChromeDriver](https://sites.google.com/a/chromium.org/chromedriver/downloads) installed and accessible. You can set the path to ChromeDriver in the script using the `--path` argument, or it will default to `/path/to/chromedriver`.

## Usage

To scrape NCBI search results, run the script with the following options:

```bash
python pubmed_scraper.py -u <PUBMED_URL> -o <OUTPUT_CSV> [-p <CHROMEDRIVER_PATH>]
```

### Arguments

- `-u`, `--url`: The URL of the NCBI search page to scrape.
- `-o`, `--output_csv`: The name of the output CSV file where the results will be saved.
- `-p`, `--path` (optional): The path to the ChromeDriver executable. If not provided, it defaults to `/home/koala/biotools/bin/chromedriver`.

## Examples

### Basic Usage with Default ChromeDriver Path

```bash
python your_script_name.py -u "https://www.ncbi.nlm.nih.gov/pmc?term=(Reverse%20Vaccinology%5BBody%20-%20Key%20Terms%5D)%20AND%20%22Frontiers%20in%20Immunology%22%5BJournal%5D" -o "./results/ncbi_frontiers_articles.csv"
```

### Specifying a Different ChromeDriver Path

```bash
python your_script_name.py -u "https://www.ncbi.nlm.nih.gov/pmc?term=(Reverse%20Vaccinology%5BBody%20-%20Key%20Terms%5D)%20AND%20%22Frontiers%20in%20Immunology%22%5BJournal%5D" -o "./results/ncbi_frontiers_articles.csv" -p "/path/to/your/chromedriver"
```

## Dependencies

The script requires the following Python libraries:

- `selenium`: For automating web browser interaction.
- `beautifulsoup4`: For parsing HTML and extracting data.
- `pandas`: For data manipulation and exporting results to a CSV file.
- `argparse`: For command-line argument parsing.

You can install these dependencies using the `requirements.txt` file included in this repository.

## Contributing

Contributions are welcome! If you have suggestions for improvements or find any bugs, feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
