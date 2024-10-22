
# Break the Cloudflare Turnstile Captcha Bypass for Scraping

Sometimes we encounter Cloudflare protection when scraping websites. This script helps bypass Cloudflare protection, enabling automated interaction with websites.
Recently, [@frederik-uni](https://github.com/frederik-uni) has introduced a new feature called "Server Mode". This feature allows you to bypass the Cloudflare protection remotely, either you can get the cookies or the HTML content of the website.
# Sponsors
### [Capsolver](https://www.capsolver.com/?utm_source=github&utm_medium=ads&utm_campaign=scraping&utm_term=CloudflareBypassForScraping)

[![Capsolver](docs/capsolver.png)](https://www.capsolver.com/?utm_source=github&utm_medium=ads&utm_campaign=scraping&utm_term=CloudflareBypassForScraping)

# How does this script work?

When using Selenium, you'll find that bypassing Cloudflare protection isn't possible. Even after clicking "I'm not a robot," you'll remain stuck on the "Checking your browser before accessing" page. Cloudflare can detect automation tools and block them, trapping the webdriver on that page indefinitely. By using the DrissionPage script as a controller for the browser, it goes undetected as a webdriver and bypasses Cloudflare protection.


## Installation

You can install the required packages by running the following command:

```bash
pip install -r requirements.txt
```

## Usage

Create a new instance of the `CloudflareBypass` class and call the `bypass` method when you need to bypass the Cloudflare protection.

```python
from CloudflareBypasser import CloudflareBypasser

driver = ChromiumPage()
driver.get('https://nopecha.com/demo/cloudflare')

cf_bypasser = CloudflareBypasser(driver)
cf_bypasser.bypass()
```

You can run the test script to see how it works:

```bash
python test.py
```

# What is this not?

This script is not related to bring a solution to bypass if your IP is blocked by Cloudflare. If you are blocked by Cloudflare, you need a clean IP to access the website. This script is designed to bypass the Cloudflare protection, not to bypass the IP block.
