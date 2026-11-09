# Web Scraper (Python)

A short Python script that downloads the [Speedcafe](https://speedcafe.com) motorsport news homepage and prints every link on it. It's a starting point for web scraping, which means pulling information out of web pages with code. It uses two popular packages: [Requests](https://requests.readthedocs.io) to download the page and [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) to read the HTML.

I also used it to try out modern Python project tools on a new Mac. Each project gets its own copy of Python and its packages, like `node_modules` in a JavaScript project, so projects can't clash with each other.

## What you need

- **[uv](https://docs.astral.sh/uv/)**, a fast tool that installs Python and a project's packages for you. Install it on a Mac or Linux with:
  ```bash
  curl -LsSf https://astral.sh/uv/install.sh | sh
  ```
  (or `brew install uv`). Windows instructions are on the uv site. You don't need to install Python separately: uv downloads the right version (3.12, set in `.python-version`) automatically.

## How to run it

```bash
git clone https://github.com/DCodeAus/MacPythonProjects.git   # or Code › Download ZIP
cd MacPythonProjects
uv run web-scraping.py
```

The first run takes a few seconds while uv sets up a `.venv` folder with Python, Requests and Beautiful Soup. After that it starts instantly.

## What you'll see

A long list of the links on the page, one per line, for example:

```
https://speedcafe.com/
/
https://speedcafe.com/news/
https://speedcafe.com/supercars/
https://speedcafe.com/f1/
...
```

Links starting with `/` are on the same site (`/news/` means `https://speedcafe.com/news/`), and ones starting with `#` jump to a part of the same page. If the site replies with an error (for example 403 or 404), it prints `Failed to retrieve the webpage:` and that code instead. If you're offline, Python stops with a `ConnectionError`.

## Make it your own

- **Scrape a different site:** change the `url = 'https://speedcafe.com'` line in `web-scraping.py`.
- **Find other things:** `soup.find_all('a')` finds links. Try `soup.find_all('h2')` for headings, then print `item.get_text()` instead of `link.get('href')`.
- **Add a package:** `uv add <package-name>`.

Be polite when scraping: check a site's terms of use, and don't request pages in a fast loop.

## History: the original Rye setup

This project started out with [Rye](https://rye.astral.sh) in 2024. Rye has since been discontinued in favour of uv, which is made by the same people, so the project switched to uv in October 2026. My original setup notes are kept below for reference; you don't need them to run the project.

<details>
<summary>Rye install notes and output (2024)</summary>

Run `curl -sSf https://rye.astral.sh/get | bash`

Output

```
This script will automatically download and install rye (latest) for you.

✔ Continue? · yes
? What should running `python` or `python3` do when you are not inside a Rye man
✔ What should running `python` or `python3` do when you are not inside a Rye managed project? · Run a Python installed and managed by Rye
✔ Which version of Python should be used as default toolchain? · cpython@3.12
✔ Should the installer add Rye to PATH via .profile? · yes
Added to PATH.
note: for this to take effect you will need to restart your shell or run this manually:

    source "$HOME/.rye/env"

To make it work with zsh, you might need to add this to your .zprofile:

    source "$HOME/.rye/env"

For more information read https://rye.astral.sh/guide/installation/

All done!
```

Then run
```
source ~/.zprofile
➜ ~ echo $PATH
```
```
➜ ~ python --version
Python 3.12.6
```
```
➜ ~ python3 --version
Python 3.12.6
```

Inside the package/project you are building run:
```
✗ rye install requests
```
Output
```
Resolved 5 packages in 414ms
Prepared 5 packages in 208ms
Installed 5 packages in 5ms

- certifi==2024.8.30
- charset-normalizer==3.4.0
- idna==3.10
- requests==2.32.3
- urllib3==2.2.3
  Found additional non installed scripts in dependencies:
  charset-normalizer:

* normalizer
  To install scripts from these packages pass the appropriate --include-dep

warning: installed package did not expose any scripts
➜ WebscraperPython git:(main) ✗ rye sync
Initializing new virtualenv in /Users//WebscraperPython/.venv
Python version: cpython@3.12.6
Generating production lockfile: /Users//WebscraperPython/requirements.lock
Generating dev lockfile: /Users//WebscraperPython/requirements-dev.lock
Installing dependencies
Resolved 1 package in 0.66ms
Built webscraperpython @ file:///Users//Code/WebscraperPython
Prepared 1 package in 531ms
Installed 1 package in 1ms

- webscraperpython==0.1.0 (from file:///Users//Code/WebscraperPython)
  Done!
  ➜ WebscraperPython git:(main) ✗ python web-scraping.py
  Traceback (most recent call last):
  File "/Users/Code/WebscraperPython/web-scraping.py", line 1, in <module>
  import requests
  ModuleNotFoundError: No module named 'requests'
  ➜ WebscraperPython git:(main) ✗ rye add requests
  Added requests>=2.32.3 as regular dependency
  Reusing already existing virtualenv
  Generating production lockfile: /Users//Code/WebscraperPython/requirements.lock
  Generating dev lockfile: /Users//Code/WebscraperPython/requirements-dev.lock
  Installing dependencies
  Resolved 6 packages in 1ms
  Built webscraperpython @ file:///Users//Code/WebscraperPython
  Prepared 1 package in 210ms
  Uninstalled 1 package in 0.75ms
  Installed 6 packages in 5ms
- certifi==2024.8.30
- charset-normalizer==3.4.0
- idna==3.10
- requests==2.32.3
- urllib3==2.2.3
  ~ webscraperpython==0.1.0 (from file:///Users/WebscraperPython)
  Done!
  ➜ WebscraperPython git:(main) ✗ rye add bs4
  Added bs4>=0.0.2 as regular dependency
  Reusing already existing virtualenv
  Generating production lockfile: /Users/
  requirements.lock
  Generating dev lockfile: /Users/
  requirements-dev.lock
  Installing dependencies
  Resolved 9 packages in 1ms
  Built webscraperpython @ file:///
  Prepared 4 packages in 210ms
  Uninstalled 1 package in 0.62ms
  Installed 4 packages in 3ms
- beautifulsoup4==4.12.3
- bs4==0.0.2
- soupsieve==2.6
  ~ webscraperpython==0.1.0 (from file:///
  Done!
```
  

</details>
