# Intro to Selenium
  
**Definition/Overview:** Selenium is an open-source automated web app testing tool/library suite that is compatible with various platforms (including all of the popular contemporary web browsers). Its main components include Selenium IDE, Selenium Grid, and Selenium WebDriver. A previous component, Selenium Remote Control/RC, has been deprecated (in favor of Selenium WebDriver).

#### Table of Contents

1. [Selenium Components](#components)
2. [Advantages/Limitations](#advslims)
3. [Important Methods](#methods)
4. [Implicit and Explicit Waits](#waits)
  
<hr />
  
## 1. <a name="components">Selenium Components</a>

**Selenium IDE** is a record-and-playback interface, available as a Chrome extension or Firefox add-on, that serves as its own integrated development environment (hence, the name 'Selenium IDE'). It records browser testing and web data selection scripts in 'Selenese' (a Selenium-based scripting language), which work in tandem with the HTML of user interface elements for guiding the mechanics of testing.

**Selenium Grid** is a server tool that executes parallel remote tests on multiple devices conveniently (as Selenium Grid serves as its own central hub) and quickly (processor efficiently). High availability is promoted via load balancing and the mitigation of single point of failure potential for the system.

**Selenium WebDriver** is a web automation tool that enables cross-browser tests to be executed. It does so without requiring its own unique server: it takes commands and forwards them directly to an instance of the browser, which it initiates. It supports complex scripting and has a wide range of programming language, framework, and browser compatibility.

## 2. <a name="advslims">Advantages/Limitations</a>
  
**Advantages of Selenium include:**
  
* Free use (and open source, with a thriving community for support).
* Support for various platforms/browsers.
* Seamless integration with various testing tools (such as Maven, JUnit, and TestNG).
* Compatibility with assorted programming languages (such as Java, Python, Ruby, JavaScript, and C#).
  
**Limitations of Selenium include:**
  
* Desktop app testing support is not native (although such tools can be integrated with Selenium).
* Built-in reporting tools are also not native (although these can also be integrated).
* Support for image and CAPTCHA handling is (natively) limited.
* Mobile testing requires integration with non-native tools (such as Appium).

## 3. <a name="methods">Important Methods</a>
  
**isDisplayed()**: Verifies if a specified element is visible on a page.  
**isEnabled()**: Verifies if a specified element is toggled on for interaction on a page.  
**isSelected()**: Verifies if a checkbox or radio buttion has been chosen by the user.  
  
**findElement()**: Retrieves one specified WebElement.  
**findElements()**: Returns a list from the specified WebElements (or an empty list, should none of the WebElements be found).  
**getText():** Returns the displayed inner text of a WebElement.  
**getAttribute():** Returns the value of a specified WebElement attribute.  
**doubleClick():** Executes a double-click on a WebElement, using the Actions class.  
  
**driver.manage().window().maximize():** Sets the browser window to full size.  
**driver.close():** Closes the presently open browser window.  
**driver.quit():** Closes every browser window that WebDriver has open.  
  
**getWindowHandles():** Retrives all window handles.  
**switchTo().window():** Handles and moves between browser windows/tabs.  
**switchTo().frame():** Handles and moves between frames (including iframes).  
  
**navigate().to():** Moves to a specified web address.  
**get():** Navigates to a specified web address *and* waits for the page to load in its entirety.  
  
**sendKeys():** Inputs a file's path into an upload file, simulating a file upload.  
  
**navigate().refresh():** Refreshes a browser window/page.  
**driver.get(driver.getCurrentUrl()):** Reloads the current URL *and* refreshes the browser window.  
  
## 4. <a name="waits">Implicit and Explicit Waits</a>
  
* **Implicit Wait:** Applies to each element. Sets a default wait time if an element is not found.
* **Explicit Wait:** Applies to specified elements/conditions.
  + **Fluent Wait:** A unique explicit wait that sets conditions and polling frequencies for waiting (not relying upon default wait values).
  + **WebDriverWait**: A unique explicit wait that waits for a specified element or condition before throwing an exception.
