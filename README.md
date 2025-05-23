# IBDB Data Scraper

This Python script scrapes show details from the [Internet Broadway Database (IBDB)](https://www.ibdb.com/shows) and stores them in a CSV file. It uses Selenium and BeautifulSoup to navigate the dynamic web pages and extract structured information.

## Features

- Extracts details such as:
  - Show title
  - Opening date
  - Poster image link
  - Theatre name
  - Show type
  - Detail page URL
- Deduplicates entries based on title and date.
- Automatically saves new data to `shows.csv`.

## Requirements

Make sure you have the following installed:

- Python 3.7+
- Google Chrome
- ChromeDriver (must match your Chrome version)

### Python Packages

Install the dependencies with:

```bash
pip install selenium beautifulsoup4 pandas
```

## Usage

To run the scraper:

```bash
python ibdb_scraper.py
```

This will:

1. Launch a Chrome browser instance.
2. Navigate to the IBDB current shows page.
3. Visit each show's detail page.
4. Extract relevant information.
5. Save the data in a file named `shows.csv`.

## File Structure

- `ibdb_scraper.py`: Main script to run the scraper.
- `shows.csv`: Output file storing all scraped show data (auto-created if it doesn't exist).

## Notes

- The script has a built-in delay (`time.sleep(5)`) to ensure pages load fully before parsing.
- If a timeout or page structure change occurs, the script will handle it and continue.
- Make sure ChromeDriver is accessible via your system `PATH`.

## Limitations

- The script is tightly coupled with the current HTML structure of IBDB and may break if the site layout changes.
- Long runtime due to delays and page loads—meant for infrequent scheduled scraping.

## License

MIT License