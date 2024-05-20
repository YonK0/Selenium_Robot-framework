# Selenium_Robot-framework
Many people struggling using chrome profile in Robot Framework , specially for the new Selenium version  


![RhwL](https://github.com/YonK0/Selenium_Robot-framework/assets/63075415/bbc771bc-349e-499f-839f-88e964a550e9)


So this is the right way to do it :
```
*** Keywords ***
Open Browser With Profile
    ${options}=    Evaluate    sys.modules['selenium.webdriver'].ChromeOptions()    sys, selenium.webdriver
    Call Method    ${options}    add_argument    --allow-running-insecure-content
    Call Method    ${options}    add_argument    --disable-web-security
    Call Method    ${options}    add_argument    --user-data-dir\=/Users/user_name/AppData/Local/Google/Chrome/User Data
    Create WebDriver    Chrome    options=${options}
    Go To   https://github.com/YonK0
