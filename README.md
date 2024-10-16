# webscraperpython

#Webscraper using beautiful soup and Python.

This points towards a site with multiple references to feed through the scraper, as opposed to a very basic demo that was provided when I was first setting this out.

This is part of the testing of the setup of a new Mac testing the Rye package suite.
Similar to node/npm where python is installed within the project as opposed to globally on the computer. Maybe suited better towards development to avoid conflicts as it installs the correct package you are after within the project. Great for maintainence of old tooling systems when migrating to newer versions.

##To install rye
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

All done!```

Then run
source ~/.zprofile
➜ ~ echo $PATH

➜ ~ python --version
Python 3.12.6
➜ ~ python3 --version
Python 3.12.6

Inside the package/project you are building

✗ rye install requests
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
  #Run web-scraping.py
  `➜ WebscraperPython git:(main) ✗ python web-scraping.py`
  https://www.iana.org/domains/example
  `➜ WebscraperPython git:(main) ✗ python web-scraping.py`
  Output
```
  https://speedcafe.com/news/
  /motorsport-event-calendar
  https://speedcafe.com/results/
  https://speedcafe.com/podcasts/
  /speedcafe-tv/
  https://www.jobstop.com/
  https://www.networkcafe.com.au/
  https://speedcafe.com/contact/
  https://speedsales.com.au/
  https://torquecafe.com/
  https://speedcafe.com/speedcafe-photo-comp/
  https://www.facebook.com/speedcafe
  https://www.instagram.com/speedcafe/
  https://twitter.com/speedcafe
  https://www.youtube.com/@speedcafetv
  #jeg_loginform
  #jeg_registerform
  

#

https://speedcafe.com/

#

/
https://speedcafe.com/supercars/
https://speedcafe.com/supercars/super2/
https://speedcafe.com/supercars/super3/
https://speedcafe.com/calendar/supercars/
https://speedcafe.com/f1/
https://speedcafe.com/f1/drivers/
https://speedcafe.com/f1/formula-2/
https://speedcafe.com/f1/formula-3/
https://speedcafe.com/calendar/f1/
https://speedcafe.com/nascar/
https://speedcafe.com/indycar/
https://speedcafe.com/gt/
https://speedcafe.com/gt/
https://speedcafe.com/gt/bathurst-12-hour/
https://speedcafe.com/gt/gt-australia/
https://speedcafe.com/gt/gt-europe/
https://speedcafe.com/live-stream-imsa-sportscar-championship-petit-le-mans-road-atlanta/
https://speedcafe.com/live-stream-imsa-sportscar-championship-petit-le-mans-road-atlanta/
https://speedcafe.com/

```
