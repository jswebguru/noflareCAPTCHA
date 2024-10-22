
# Break the Cloudflare Turnstile Captcha Bypass for Scraping

Sometimes we encounter Cloudflare protection when scraping websites. This script helps bypass Cloudflare protection, enabling automated interaction with websites.
Recently, [@frederik-uni](https://github.com/frederik-uni) has introduced a new feature called "Server Mode". This feature allows you to bypass the Cloudflare protection remotely, either you can get the cookies or the HTML content of the website.

# How does this script work?

When using Selenium, you'll find that bypassing Cloudflare protection isn't possible. Even after clicking "I'm not a robot," you'll remain stuck on the "Checking your browser before accessing" page. Cloudflare can detect automation tools and block them, trapping the webdriver on that page indefinitely. By using the DrissionPage script as a controller for the browser, it goes undetected as a webdriver and bypasses Cloudflare protection.

# What Is Cloudflare Bot Management
Cloudflare is a content delivery and web security company. It provides a Web Application Firewall (WAF) to defend websites against security threats, such as cross-site scripting (XSS), credential stuffing, and DDoS attacks.

One of the core systems of Cloudflare's WAF is the Bot Manager, which mitigates attacks from malicious bots without impacting real users. However, Cloudflare acknowledges the importance of bots such as Google and other search engine crawlers that make content discoverable, so it maintains an allowlist for these good bots.

However, Cloudflare assumes that any unknown bot traffic, including web scrapers, is malicious. Your scraper may be denied access to a Cloudflare-protected web page regardless of your intent.

If you've ever tried to scrape a Cloudflare-protected site, you might have run into a few of the following bot-manager-related errors:

Error 1003: Direct IP access not allowed.
Errors 1006, 1007, and 1008: Access denied.
Error 1009: Access denied due to your region.
Error 1010: Access denied due to suspicious browser signature.
Error 1015: Your access rate has been limited.
Error 1020: Access denied because your request looks malicious.
These challenges are often accompanied by a Cloudflare 403 Forbidden HTTP response status code.


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
