# GitHub Repositories Scraper

This Python script scrapes data from GitHub repositories and saves the information to a CSV file.

## Features

- Retrieves the repository name, number of stars, number of forks, and the repository URL.
- Supports scraping from a single repository URL or a search page with multiple repositories.
- Saves the scraped data to a CSV file named `repository_info.csv`.

## Dependencies

The script requires the following Python libraries:

- `requests`: for making HTTP requests to GitHub.
- `BeautifulSoup`: for parsing the HTML content of the GitHub pages.
- `pandas`: for storing and saving the scraped data in a CSV format.

## Functions

- get_repo_name(doc): Extracts the repository names from the HTML document.
- get_stars(doc): Extracts the number of stars for each repository.
- get_forks(doc): Extracts the number of forks for each repository.
- get_repo_url(doc, base_url): Constructs the full repository URLs based on the base URL.
- scrape_github_id(repo_url): Scrapes data for a single repository URL and returns a pandas DataFrame.
- Mega_scrape(repo_url): Scrapes data for a search page with multiple repositories and saves the results to a CSV file.

## Run Code

``Mega_scrape('https://github.com/search?q=topic%3Apython&type=Repositories')`` <br>
This will scrape data for all the repositories displayed on the search page and save the results to a CSV file named repository_info.csv.

``df = scrape_github_id('https://github.com/pandas-dev/pandas')`` <br>
This will scrape data for the specified repository and return a pandas DataFrame.

## Notes

- The script assumes that the GitHub page structure remains consistent. If the HTML layout changes, the script may need to be updated accordingly.
- The script currently supports scraping up to 30 repositories per page. If the search results exceed 30 repositories, the script will automatically navigate to the next       page and continue scraping.
- The scraped data is saved to a CSV file named repository_info.csv in the same directory as the script.
