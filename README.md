# Comics to PDF
A tool to download comic books as PDF files from [ReadComicOnline](https://readcomiconline.li) for offline use.

## Tech Stack
Python, Selenium, Pillow, Tenacity (Retry module)

## How It Works
1. Enter the URL of the comic series you want to download.
2. In a headless browser, Selenium scrapes the webpage for each each issue (book) in the series.
3. For each issue (book)'s webpage, it scrapes the images (page scans) and downloads them.
4. Finally, each issue's images are combined into a PDF file.

## Running the project locally
1. Install the dependencies, optionally in a virtual environment. `pip install -r requirements.txt`
2. Run the Jupyter Notebook file.

## Challenges
One challenge was handling occasional redirects to CAPTCHA pages since CAPTCHAs can't be resolved in a headless browser. To resolve this, whenever the browser encountered a CAPTCHA page, I opened a separate "headful"/"headed" browser to the CAPTCHA page. After the user resolves it, the headless browser retries its URL and no longer redirects to the CAPTCHA page.

## Lessons Learned:
I learned to gracefully handle errors with try/except blocks and retry code with the Tenacity (retry) module.

I also learned to scrape webpages with Selenium.


## Disclaimer
This project is intended for educational purposes only. I do not condone the use any web scrapers for illegal, unethical or commercial purposes.

[ReadComicOnline] does not explicitly forbid web scrapping.