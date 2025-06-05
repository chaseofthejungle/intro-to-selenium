# Intro to Selenium
  
**Definition/Overview:** [Selenium](https://www.selenium.dev/) is an open-source automated web app testing tool/library suite that is compatible with various platforms (including all of the popular contemporary web browsers). Its main components include Selenium IDE, Selenium Grid, and Selenium WebDriver. A previous component, Selenium Remote Control/RC, has been deprecated (in favor of Selenium WebDriver).
  
#### Table of Contents

1. [Selenium Components](#components)
2. [Advantages/Limitations](#advslims)
3. [Interacting with WebElements](#elements)
4. [Implicit and Explicit Waits](#waits)
5. [Exception Handling](#exceptions)
6. [Other Classes and Interfaces](#others)
7. [Test Automation Alternatives](#alternatives)
8. [Supplemental Resources](#supplemental)
  
<hr />
  
## 1. <a name="components">Selenium Components</a>

**Selenium IDE** is a record-and-playback interface, available as a Chrome extension or Firefox add-on, that serves as its own integrated development environment (hence, the name 'Selenium IDE'). It records browser testing and web data selection scripts in 'Selenese' (a Selenium-based scripting language), which work in tandem with the HTML of user interface elements for guiding the mechanics of testing.

**Selenium Grid** is a server tool that executes parallel remote tests on multiple devices conveniently (as Selenium Grid serves as its own central hub) and quickly (processor efficiently). High availability is promoted via load balancing and the mitigation of single point of failure potential for the system.

**Selenium WebDriver** is a web automation tool that enables cross-browser tests to be executed. It does so without requiring its own unique server: it takes commands and forwards them directly to an instance of the browser, which it initiates. It supports complex scripting and has a wide range of programming language, framework, and browser compatibility.
  
* While WebDriver is utilized for local browser automation, *Remote WebDriver* can be used to automate a web browser on a remote server (if it is running Selenium Grid).

<hr />
  
## 2. <a name="advslims">Advantages/Limitations</a>
  
**Advantages of Selenium include:**
  
* Free use (and open source, with a thriving community for support).
* Support for various platforms/browsers.
* Seamless integration with various test case management, reporting, CI/CD, and other tools (such as Maven, Jenkins, JUnit, and TestNG).
* Compatibility with assorted programming languages (such as Java, Python, Ruby, JavaScript, and C#).
* If a browser is run as a headless browser (e.g., PhantomJS, Chrome headless) rather than in standard mode, it does not use a graphical user interface (GUI).
  
**Limitations of Selenium include:**
  
* Desktop app testing support is not native, although relevant tools (e.g., Robot Framework, AutoIt) can be integrated *with* Selenium.
* Built-in reporting tools are also not native (although these can also be integrated).
* Support for image and CAPTCHA handling is (natively) limited.
  + However, CAPTCHAs might be automated through complex means, such as applying algorithms to decode images using Optical Character Recognition (OCR).
* Mobile testing requires integration with non-native tools (such as Appium).
  
<hr />
  
## 3. <a name="elements">Interacting with WebElements</a>
  
A *WebElement* is a web page element (e.g., input box, button) that Selenium can interface with. WebElements can be located by Selenium through a variety of locators, such as: XPath, Name, Tag Name, Class Name, ID, Link Text (or Partial Link Text), and CSS Selector.
    
* The **Actions** class enables keyboard and mouse event simulation (e.g., clicking, clicking and holding, pressing the up or down keys).
  + *For example:* The Actions class can be used to call the clickAndHold() method on a WebElement.
* **Page Object Model (POM)** is a design pattern in which an object repository for web elements is created. This enables tests to have increased readability and maintainability.
  + A *Page Factory* is a POM implementation that provides annotations (e.g., @FindBy) to readily initialize web elements.
* **XPath**: This query language selects nodes from HTML and XML documents. It utilizes two kinds of XPaths...
  + Absolute (starting from root nodes, using full paths)
  + Relative (starting from the middle of the Document Object Model's, or DOM's structure).
  
*Important methods for interacting with WebElements include:*
  
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
    
<hr />
  
## 4. <a name="waits">Implicit and Explicit Waits</a>
  
* **Implicit Wait:** Applies to *each* element. Sets a default wait time if an element is not found.
* **Explicit Wait:** Applies to *specified* elements/conditions.
  + **Fluent Wait:** A unique explicit wait that sets conditions and polling frequencies for waiting (not relying upon default wait values).
  + **WebDriverWait**: A unique explicit wait that waits for a specified element or condition before throwing an exception.
  
<hr />
  
## 5. <a name="exceptions">Exception Handling</a>
  
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
  
<hr />
  
## 6. <a name="others">Other Classes and Interfaces</a>
  
* **ChromeDriver** and **FirefoxDriver**: These are examples of WebDriver interfaces that execute Selenium tests in their respective web browsers.
  + Cross-browser testing can also be accomplished using tools (e.g., TestNG) that accept *browser-based parameters*.
* **DesiredCapabilities**: This class can set values for web browser properties/keys (e.g., version, platform, browser name) before initiating a WebDriver session.
  + DesiredCapabilities can configure proxy servers, which can be utilized in testing environments to route traffic through a middle layer.
* **JavascriptExecutor**: This interface enables JavaScript code to be ran within a web browser (such as for scrolling, or to handle dynamic events).
* **TakesScreenshot**: This WebDriver interface can capture screenshots.
* **TestNG**: This is a testing framework that integrates with Selenium to manage test cases, execute parallel tests, handle assertions, and generate reports.  
  
<hr />
  
## 7. <a name="alternatives">Test Automation Alternatives</a>
  
* Some test automation alternatives to Selenium include:
  + [**Cucumber**](https://cucumber.io/): An open-source Ruby-based testing tool for simplified, English-based test case writing.
  + [**Cypress**](https://www.cypress.io/): Built for complex, contemporary front-end web testing. Intended for JavaScript development.
  + [**NightwatchJS**](https://nightwatchjs.org/): A tool for Node.js-based, automated end-to-end web asset testing (including across browsers).
  + [**Playwright**](https://playwright.dev/): An open-source Node.js-based framework for automated web testing.
  + [**Puppeteer**](https://pptr.dev/): A JavaScript library that performs headless browser testing by default.
  + [**TestCafe**](https://testcafe.io/): Used for building quick JavaScript and TypeScript testing configurations.
  + [**UFT One**](https://admhelp.microfocus.com/uft/en/23.4-24.2/UFT_Help/Content/User_Guide/Ch_UFT_Intro.htm): Supports VBScript-based test scripts.
    - Selenium offers open-source, community, cross-platform and multiple programming language support that UFT One does not presently provide.
  
<hr />
  
## 8. <a name="supplemental">Supplemental Resources</a>

* *[API Testing Overview Guide](https://github.com/chaseofthejungle/api-testing-and-performance-guide)*
* *[Official Selenium Website](https://www.selenium.dev/)*
* *[Selenium Actions API](https://www.selenium.dev/documentation/webdriver/actions_api/)*
  
<hr />
  
TODO: Add Selenium IDE screenshots, organize the WebElement methods section, and add information on installation/setup.
