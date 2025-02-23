# Intro to Selenium
  
**Definition/Overview:** Selenium is an open-source automated web app testing tool/library suite that is compatible with various platforms (including all of the popular contemporary web browsers). Its main components include Selenium IDE, Selenium Grid, and Selenium WebDriver. A previous component, Selenium Remote Control/RC, has been deprecated (in favor of Selenium WebDriver).
  
<hr />
  
## Selenium Components

**Selenium IDE** is a record-and-playback interface, available as a Chrome extension or Firefox add-on, that serves as its own integrated development environment (hence, the name 'Selenium IDE'). It records browser testing and web data selection scripts in 'Selenese' (a Selenium-based scripting language), which work in tandem with the HTML of user interface elements for guiding the mechanics of testing.

**Selenium Grid** is a server tool that executes parallel remote tests on multiple devices conveniently (as Selenium Grid serves as its own central hub) and highly processor efficiently. High availability is promoted via load balancing and the mitigation of single point of failure potential for the system.

**Selenium WebDriver** is a web automation tool that enables cross-browser tests to be executed. It does so without requiring its own unique server: it takes commands and forwards them directly to an instance of the browser, which it initiates.

## Advantages/Limitations:
  
**Advantages of Selenium include:**
  
* Free use (and open source, with a thriving community for support).
* Support for various platforms/browsers.
* Seamless integration with various testing tools (such as Maven, JUnit, and TestNG).
* Compatibility with assorted programming languages (such as Java, Python, Ruby, JavaScript, and C#).
  
**Limitations of Selenium include:**
  
* Desktop app testing support is not native (although such tools can be integrated with Selenium).
* Built-in reporting tools are also not native (although these can also be integrated).
* Support for image and CAPTCHA handling is (natively) limited.
* Mobile testing is likely to require non-native tools (such as Appium).
