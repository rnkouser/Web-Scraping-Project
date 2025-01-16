# Amazon Product Title Scraper

This script demonstrates how to scrape the title of a product from an Amazon product page using Python's `requests` and `BeautifulSoup` libraries.

## Features
- Fetches the HTML content of an Amazon product page.
- Parses the HTML using `BeautifulSoup` to extract the page title.
- Prints the product title to the console.

## Prerequisites
Ensure you have the following installed:

1. Python 3.x
2. `requests` library
3. `beautifulsoup4` library

Install the required libraries by running:
```bash
pip install requests beautifulsoup4
```

## Code Example
```python
import requests
from bs4 import BeautifulSoup

# Fetch the HTML content of the Amazon product page
req = requests.get("https://www.amazon.ca/amazon-fire-tv-stick-hd/dp/B0CQN248PX?pd_rd_w=wJMS2&content-id=amzn1.sym.39526d57-066e-456c-bc01-eab1026394a8&pf_rd_p=39526d57-066e-456c-bc01-eab1026394a8&pf_rd_r=XCK0BD2XJZ4KCKBM40H0&pd_rd_wg=o3ptG&pd_rd_r=438e1871-25be-41e0-8175-a56817d4a7ed&pd_rd_i=B0CQN248PX&ref_=pd_hp_d_btf_unk_B0CQN248PX/")

# Parse the HTML using BeautifulSoup
soup = BeautifulSoup(req.content, "html.parser")

# Extract the title of the page
res = soup.title

# Print the title to the console
print(res.get_text())
```

## How It Works
1. **Fetch Content:** The `requests.get()` function fetches the HTML content from the provided Amazon URL.
2. **Parse HTML:** The `BeautifulSoup` object parses the HTML content.
3. **Extract Title:** The `.title` attribute retrieves the title tag of the page, and `.get_text()` fetches its text content.

## Example Output
If the script successfully fetches the product page, it will print the title of the product, e.g.,
```
Amazon Fire TV Stick with Alexa Voice Remote (includes TV controls), HD streaming device
```

## Notes
- Ensure you have permission to scrape the website, as web scraping may violate Amazon's terms of service.
- Amazon may block requests or serve CAPTCHA if too many requests are made.
- Use headers or proxies responsibly to avoid being flagged.

## Contribution
Feel free to contribute to this project by forking the repository and submitting a pull request.
