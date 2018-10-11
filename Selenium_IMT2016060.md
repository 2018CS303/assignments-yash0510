# Selenium Install

Selenium is a web automation tool. A web browser can be controlled using Python code, any task you would normally do on the web can be done using the selenium module. 
Install selenium using the below command:
```sh
pip install -U selenium
```

# Chrome Driver Setup:

ChromeDriver is a separate executable that WebDriver uses to control Chrome. It is maintained by the Chromium team with help from WebDriver contributors. 

Follow the steps to install the chrome driver:
**Step 1:** First, ensure Chromium/Google Chrome is installed in a recognized location.
**Step 2:** Download ChromeDriver.exe from the link below: 
```sh
https://sites.google.com/a/chromium.org/chromedriver/downloads
```
**Step 3:** Executing the Test Script in Chrome Browser
- Find the sample script (using py) mentioned below to run test script in Chrome browser. Execute it to run the test in Chrome browser which will first open chrome browser and then open the appropriate URL mentioned in the script.
- Set a system property “webdriver.chrome.driver” to the path of executable file “Chromedriver.exe“. If you miss doing this, an error `“The path to the driver executable must be set by the webdriver.chrome.driver system property“.` will be displayed.
- Instantiate *ChromeDriver* class
```sh
from selenium import webdriver
from selenium.webdriver.common.keys import Keys

browser = webdriver.Chrome()

browser.get('http://www.google.com')
print(browser.title)

browser.quit()
```

# Adding a Headless argument

If we don't want the browser to exhibit and want the tests to happen in the background, modify the above written code. Then, write ChromeOptions() instead of just using Chrome() and then add a "headless" argument to it.
Below is the code that have the same logic as the code above but without displaying the browser:

```sh
from selenium import webdriver
from selenium.webdriver.common.keys import Keys

options = webdriver.ChromeOptions()
options.add_argument('headless')
browser = webdriver.Chrome(options = options)

browser.get("http://www.google.com")
print(browser.title)

browser.close()
```
