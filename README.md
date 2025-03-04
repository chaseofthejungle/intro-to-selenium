# Intro to Selenium
  
**Definition/Overview:** Selenium is an open-source automated web app testing tool/library suite that is compatible with various platforms (including all of the popular contemporary web browsers). Its main components include Selenium IDE, Selenium Grid, and Selenium WebDriver. A previous component, Selenium Remote Control/RC, has been deprecated (in favor of Selenium WebDriver).

#### Table of Contents

1. [Selenium Components](#components)
2. [Advantages/Limitations](#advslims)
3. [Important Methods](#methods)
4. [Implicit and Explicit Waits](#waits)
5. [Miscellaneous](#misc)
  
<hr />
  
## 1. <a name="components">Selenium Components</a>

**Selenium IDE** is a record-and-playback interface, available as a Chrome extension or Firefox add-on, that serves as its own integrated development environment (hence, the name 'Selenium IDE'). It records browser testing and web data selection scripts in 'Selenese' (a Selenium-based scripting language), which work in tandem with the HTML of user interface elements for guiding the mechanics of testing.

**Selenium Grid** is a server tool that executes parallel remote tests on multiple devices conveniently (as Selenium Grid serves as its own central hub) and quickly (processor efficiently). High availability is promoted via load balancing and the mitigation of single point of failure potential for the system.

**Selenium WebDriver** is a web automation tool that enables cross-browser tests to be executed. It does so without requiring its own unique server: it takes commands and forwards them directly to an instance of the browser, which it initiates. It supports complex scripting and has a wide range of programming language, framework, and browser compatibility.

## 2. <a name="advslims">Advantages/Limitations</a>
  
**Advantages of Selenium include:**
  
* Free use (and open source, with a thriving community for support).
* Support for various platforms/browsers.
* Seamless integration with various test case management, reporting, CI/CD, and other tools (such as Maven, Jenkins, JUnit, and TestNG).
* Compatibility with assorted programming languages (such as Java, Python, Ruby, JavaScript, and C#).
  
**Limitations of Selenium include:**
  
* Desktop app testing support is not native, although relevant tools (e.g., Robot Framework, AutoIt) can be integrated *with* Selenium.
* Built-in reporting tools are also not native (although these can also be integrated).
* Support for image and CAPTCHA handling is (natively) limited.
  + However, CAPTCHAs might be automated through complex means, such as applying algorithms to decode images using Optical Character Recognition (OCR).
* Mobile testing requires integration with non-native tools (such as Appium).

## 3. <a name="methods">Important Methods</a>
  
*Note: A *WebElement* is a web page element (e.g., input box, button) that Selenium can interface with.*
  
`isDisplayed()`: Verifies if a specified element is visible on a page.  
`isEnabled()`: Verifies if a specified element is toggled on for interaction on a page.  
`isSelected()`: Verifies if a checkbox or radio buttion has been chosen by the user.  
  
`findElement()`: Retrieves one specified WebElement.  
`findElements()`: Returns a list from the specified WebElements (or an empty list, should none of the WebElements be found).  
`getText()`: Returns the displayed inner text of a WebElement.  
`getAttribute()`: Returns the value of a specified WebElement attribute.  
`doubleClick()`: Executes a double-click on a WebElement, using the Actions class.  
  
`driver.manage().window().maximize()`: Sets the browser window to full size.  
`driver.close()`: Closes the presently open browser window.  
`driver.quit()`: Closes every browser window that WebDriver has open.  
  
`getWindowHandles()`: Retrives all window handles. (A *window handle* is a unique ID belonging to an individual window. A *window title* is a name displayed by a window's title bar.)
`switchTo().window()`: Handles and moves between browser windows/tabs.  
`switchTo().frame()`: Handles and moves between frames (including iframes).  
`switchTo().alert()`: Handles JavaScript prompts, alerts, and confirmation boxes. (This method handles *JavaScript* pop-ups. Selenium does not handle windows-based popups unless a utility such as Robot class or AutoIt is implemented.)
  
`navigate().to()`: Moves to a specified web address.  
`get()`: Navigates to a specified web address *and* waits for the page to load in its entirety.  
  
`sendKeys()`: Inputs a file's path into an upload file, simulating a file upload.  
  
`navigate().refresh()`: Refreshes a browser window/page.  
`driver.get(driver.getCurrentUrl())`: Reloads the current URL *and* refreshes the browser window.  
  
## 4. <a name="waits">Implicit and Explicit Waits</a>
  
* **Implicit Wait:** Applies to *each* element. Sets a default wait time if an element is not found.
* **Explicit Wait:** Applies to *specified* elements/conditions.
  + **Fluent Wait:** A unique explicit wait that sets conditions and polling frequencies for waiting (not relying upon default wait values).
  + **WebDriverWait**: A unique explicit wait that waits for a specified element or condition before throwing an exception.
  
## 5. <a name="misc">Miscellaneous</a>
  
* WebElements can be located by Selenium through a variety of locators, such as: XPath, Name, Tag Name, Class Name, ID, Link Text (or Partial Link Text), and CSS Selector.
* While WebDriver is utilized for local browser automation, *Remote WebDriver* can be used to automate a web browser on a remote server (if it is running Selenium Grid).
* To execute tests in multiple browsers while using Selenium, use the relevant WebDriver interfaces (e.g., ChromeDriver, FirefoxDriver).
  + Cross-browser testing can also be accomplished using tools (e.g., TestNG) that accept browser-based parameters.
* The testing framework *TestNG* integrates with Selenium to manage test cases, execute parallel tests, handle assertions, and generate reports.
* Some test automation alternatives to Selenium include: Cucumber, Cypress, NightwatchJS, Playwright, Puppeteer, and TestCafe.
  + *QTP/UFT* is another alternative, but Selenium offers open-source, community, cross-platform and multiple programming language support that QTP/UFT does not immediately provide.
* If a browser is run as a headless browser (e.g., PhantomJS, Chrome headless) rather than in standard mode, it does not use a graphical user interface (GUI).
* Screenshots can be captured by Selenium if using the TakesScreenshot interface in Selenium WebDriver.
* The *XPath* query language selects nodes from HTML and XML documents. It utilizes absolute (starting from root nodes, using full paths) and relative (starting from the middle of the Document Object Model's structure) XPaths.
* Page Object Model (POM) is a design pattern in which an object repository for web elements is created. This enables tests to have increased readability and maintainability.
  + A *Page Factory* is a POM implementation that provides annotations (e.g., @FindBy) to readily initialize web elements.
* Examples of common exceptions in Selenium include...
  + **NoSuchElementException**: Thrown if a specified WebElement is not found (using the provided locator) by WebDriver.
  + **NoSuchFrameException**: Thrown if WebDriver cannot find a specified frame (or iframe) via a specified frame identifier.
  + **NoSuchSessionException**: Thrown if a browser session has become inactive.
  + **NoSuchWindowException**: Thrown if WebDriver cannot find a browser window (or tab) that it needs to interface with.
  + **NoAlertPresentException**: Thrown if WebDriver attempts interaction with an alert that is not available (or has already been closed in the browser).
  + **InvalidSelectorException**: Can be thrown by WebDriver due to unsupported or overly complex expressions, invalid XPath and/or CSS expressions, and selector syntax and type errors. 
  + **ElementNotSelectableException**: Thrown by WebDriver if an element is found within the DOM but cannot be selected and have actions performed upon it.
  + **ElementNotVisibleException**: Thrown by WebDriver if a script attempts to interface with a WebElement that the user would be unable to interact with due to it being hidden (invisible).
  + **StaleElementReferenceException**: Thrown if WebDriver attempts interaction with an element that is not associated with a DOM element.
  + **TimeoutException**: Thrown by WebDriver if a command does not finish running within its allotted time.
* The Actions class enables keyboard and mouse event simulation (e.g., clicking, clicking and holding, pressing the up or down keys).
  + *For example:* The Actions class can be used to call the clickAndHold() method on a WebElement.
* *JavascriptExecute* enables JavaScript code to be ran within a web browser (such as for scrolling, or to handle dynamic events).
* *DesiredCapabilities* can set values for web browser properties (e.g., version, platform, browser name) before initiating a WebDriver session.
  + DesiredCapabilities can configure proxy servers, which can be utilized in testing environments to route traffic through a middle layer.
  
<hr />
  
TODO: Split 'Miscellaneous' items into various categories.
