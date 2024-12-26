# appium-cucumberbdd-testng
Appium mobile test automation framework with Page Object Model design using Java + Cucumber + Maven + TestNG.
Framework follows many of the industry best practices and supports Android and iOS in a single code base.

Technologies/Tools used in building the framework
=================================================
- IntelliJ - IDE
- Appium - Mobile Automation library
- Maven - Build automation tool
- Java - Programming language
- Cucumber - BDD
- Gherkin - DSL
- TestNG - Test Management library
- Log4J - Logging framework
- Extent Reports - Reporting framework
- JSON - Test Data
- XML - Static text
- GitHub - Version control
- Jenkins - CI/CD

Appium Driver Initialization
=================================================
```java
AppiumDriver driver = new AndroidDriver(new ServerManager().getServer().getUrl(), new CapabilitiesManager().getCaps());
AppiumDriver driver = new IOSDriver(new ServerManager().getServer().getUrl(), new CapabilitiesManager().getCaps());
```

Another way -> The recommended way to provide capabilities for driver creation is to use specific option builders.For example XCUITestOptions to create a XCUITest driver instance or UiAutomator2Options to create an UiAutomator2 driver instance.

```java
- UiAutomator2Options options = new UiAutomator2Options();
   options.setPlatformName(MobilePlatform.ANDROID);  
   options.setDeviceName(deviceName);
   options.setPlatformVersion(osVersion);
   options.setAutomationName("UiAutomator2");
   options.setCapability("browserstack.user", userName);
   options.setCapability("browserstack.key", accessKey);
   driver = new AndroidDriver(new URL(url), options);
```

```java
   XCUITestOptions options = new XCUITestOptions();
   options.setDeviceName("iPhone 15 Pro Max");
   options.setPlatformVersion("17.4");
   options.setCapability("browserstack.user", userName);
   options.setCapability("browserstack.key", accessKey);
   driver = new IOSDriver(new URL(url), options);
```

Locators in Appium - @AndroidFindBy and @iOSXCUITFindBy
=========================================
In the page object model, we define locators for an element for both the platforms.
First we create a page and using appium inspector, identify locators for android and ios. Then, define them using @AndroidFindBy and @iOSXCUITFindBy respectively.


Mobile Gestures in Appium
=========================================
In Appium, mobile gestures refer to the actions that users perform on their mobile devices by touching or swiping the screen. Appium supports a variety of mobile gestures that can be used to automate mobile testing, including:

1. Long press — A tap and hold on the screen for a specified duration.
2. Swipe — A single swipe in any direction on the screen.
3. Scroll - This gesture is used to simulate a scroll action on the mobile device
4. Tap — A single tap on the screen.
5. Double tap — Two quick taps on the screen.
6. Pinch — A two-finger gesture used to zoom in or out.
7. Zoom — A two-finger gesture used to magnify or reduce the size of the content.
8. Drag and drop — Moving an object on the screen by dragging it with one finger and dropping it at a new location.

mobile:clickGesture -> This gesture performs click action on the given element.

driver.executeScript("mobile: clickGesture", ImmutableMap.of(
"elementId", ((RemoteWebElement) element).getId()
));



Framework implements below best practices
=========================================
- Code reusability
- Code readability
- Scalable automation (demonstrated using multiple test classes)
- Uses explicit waits
- Abstraction layer for UI commands like click, sendkeys, etc.
- Parameterization using TestNG XML and config.properties
- Abstraction layer for test data
- Abstraction layer for static text
- Supports iOS and Android
- Demonstrates how to define UI elements that are common across pages (e.g. menu bar, side bar, etc.)
- How to recover from test failure/ how to write fail-safe test cases
- Scrolling for both Android and iOS (using touch-action, uiScrollable, mobile:scroll)
- Demonstrates how to effectively capture Screenshots/Videos
- Supports parallel execution using TestNG
- Supports parallel execution on multiple real Android and iOS devices
- Start Appium server programmatically
- Supports Cucumber-HTML-Reporter plugin
- Integrated with Log4J2 Logging framework
