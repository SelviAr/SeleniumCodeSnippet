# Selenium Code Snippet

This  repository contains Selenium code snippet I have collected over the perioid from my work. I have created this page as quick reference page for  Selenium automation engineers. My thanks to all the bloggers who helped me to become  Selenium automation engineer.

- Selvi

##Table of Contents

- [Download Driver](#Driver-Download)
- [WebDriver](#setup)
    - [Firefox](#Firefox-WebDriver)
    - [Chrome](#Chrome-WebDriver)
    - [Internet Explorer Driver](#internet-explorer-driver)
    - [Safari Driver](#safari-driver)
    - [Android Driver](#android-driver)
    - [iPhone Driver](#iphone-driver)
    - [HTMLUnit Driver]()
    - [RemoteWebDriver]
    - [Headless testing]
- [Find Elements](#find-elements)    
- [License](#license)
- [Links](#links)




## Driver Download


I am **bold**



## Firefox Driver
```java
WebDriver driver = new FirefoxDriver();           //Firefox Driver
```


## Chrome Driver
```java
System.setProperty("webdriver.chrome.driver", "/path/to/chromedriver");
WebDriver driver = new ChromeDriver();
```

## Internet Explorer Driver
```java
System.setProperty("webdriver.ie.driver", "C:\\Selenium\\IEDriverServer.exe");
WebDriver driver = new InternetExplorerDriver();
```

## Safari Driver
```java
WebDriver driver = new SafariDriver();            
```

## Opera Driver
```java
DesiredCapabilities capabilities = new DesiredCapabilities(); 
capabilities.setCapability("opera.binary", "C://Program Files (x86)//Opera//opera.exe"); 
capabilities.setCapability("opera.log.level", "CONFIG"); 
WebDriver driver = new OperaDriver(capabilities); 
         
```

## Android Driver
```java
WebDriver driver = new AndroidDriver()            
```

## iPhone Driver
```java
WebDriver driver = new IPhoneDriver();            
```

## HTMLUnit Driver
```java
DesiredCapabilities capabilities = DesiredCapabilities.firefox(); 
capabilities.setBrowserName("Mozilla/5.0 (X11; Linux x86_64; rv:24.0) Gecko/20100101 Firefox/24.0"); 
capabilities.setVersion("24.0"); 
driver = new HtmlUnitDriver(capabilities); 
```

## RemoteWebDriver
```java
DesiredCapabilities safari = IOSCapabilities.iphone("Safari");
RemoteWebDriver driver = new RemoteWebDriver(new URL("http://localhost:5555/wd/hub"), safari);
```

## PhantomJS
```java
DesiredCapabilities caps = new DesiredCapabilities(); 
caps.setCapability("takesScreenshot", true); 
caps.setJavascriptEnabled(true); // not really needed; JS is enabled by default 
caps.setCapability(PhantomJSDriverService.PHANTOMJS_EXECUTABLE_PATH_ PROPERTY, "C:/phantomjs.exe"); 
WebDriver driver = new PhantomJSDriver(caps); 
```

## SauceLabs
```java
DesiredCapabilities capabilities = new DesiredCapabilities(); 
capabilities.setBrowserName(browser); 
capabilities.setCapability("version", browserVersion); 
capabilities.setCapability("platform", Platform.MAC); 
capabilities.setCapability("name", method.getName()); 
// Create the connection to SauceLabs to run the tests 
this.driver = new RemoteWebDriver( 
new URL("http://" + username + ":" + key + "@ondemand.saucelabs. com:80/wd/hub"), capabilities); 
```

## SauceLabs
```java
public static final String USERNAME = "yourusername"; 
public static final String ACCESS_KEY = "youraccesskey"; 
public static final String URL = "http://" + USERNAME + ":" + ACCESS_KEY + "@hub.browserstack.com/wd/hub"; 
DesiredCapabilities caps = new DesiredCapabilities(); 
caps.setCapability("browser", "Firefox"); 
caps.setCapability("browser_version", "23.0"); 
caps.setCapability("os", "Windows");
caps.setCapability("os_version", "XP"); 
caps.setCapability("browserstack.debug", "true"); 
//This enable Visual Logs 
driver = new RemoteWebDriver(new URL(URL), caps); 

```


## SauceLabs
```java
DesiredCapabilitiescapabillities = DesiredCapabilities.firefox(); 
capabillities.setCapability("version", "24"); 
capabillities.setCapability("platform", Platform.WINDOWS); 
capabillities.setCapability("name", "testOnCloud"); 
capabillities.setCapability("screenshot", true); capabillities.setCapability("screenrecorder", true); 
driver = new RemoteWebDriver( 
new URL ("http://ClientKey:ClientSecret@hub.testingbot.com:4444/wd/hub"), 
capabillities); 
```


## Simple Testcase
```java
driver.get("https://www.google.com");
driver.findElement(By.name("q")).sendKeys("Download selenium chrome driver");
driver.findElement(By.name("q")).clear();
driver.findElement(By.name("q")).sendKeys("Download selenium IE driver");
driver.findElement(By.id("butid")).click();
driver.findElement(By.id("butid")).submit();
System.out.println(driver.getTitle());
System.out.println(driver.getCurrentUrl());
System.out.println(driver.getPageSource());
driver.quit();

```



## Find Elements

```java
//Find element by ID:
WebElemnt we1 = driver.findElement(By.id("Elementid"))

//Find element by element name:
WebElemnt we1 = driver.findElement(By.name("ElementName"))

//Find element by tagname:, get all the links
WebElemnt we1 = driver.findElement(By.tagName("a"))

//Find element by class name:
WebElemnt we1 = driver.findElement(By.className("ElementClassName"))

//Find element by CSS Selector:
WebElemnt we1 = driver.findElement(By.cssSelector("input[value='google']"));

//Find element by element link text
WebElemnt we1 = driver.findElement(By.linkText(“click here”))

//Find element by partial element link text
WebElemnt we1 = driver.findElement(By.partialLinkText(“clic”))

//Find element by xpath
WebElemnt we1 = driver.findElement(By.Xpath(“clic”))
```

## Xpath

```java
Absolute Path
//Identifying Xpath using full path of XML
// /body is the main root node
// /div[2] describes the 3rd div child node of parent node body
// /form describes the child node form of parent node div[2]
// /input[3] describes the 2nd input child node of parent node fieldset

xpath=//body/div[2]/form/input[3]  

//Xpath Locator based on id of element:
xpath=//input[@id='name']

//Xpath Locator based on name of element: 
xpath=//input[@name='email']

//Xpath Locator based on class of element: 
xpath=//input[@class='button']

//Xpath Locator based on value of element: 
xpath=//input[@value='Submit']

//Xpath Locator based on attribute of element: 
xpath=//input[@type='search']
xpath=//body/div[3]/form/fieldset/input[@type='search']   
xpath=//body/div[3]/form/fieldset/input[@accesskey='F']   
xpath=//input[@accesskey='F']  

//XML Xpath using /descendant:: keyword
xpath=//div[@class='search-container']/descendant::input[@accesskey='F']   
xpath=//div[@class='search-container']/descendant::input[position()=2]   

//Xpath Locator based on containing text by element: 
xpath=//p[contains(text(),'Name')]
xpath=//input[contains(@id, "searchInput")]  
xpath=//input[contains(@id, "searchInput") and contains(@accesskey,"F")]   

//Writing Xpath using last()
xpath=//body/div[3]/form/input[last()-2]  
xpath=//body/div[3]/form/*[last()-3]   

//Using starts-with keyword
xpath=//input[starts-with(@type, "s")]    

//Using OR (|) condition with xpath
xpath=//input[@accesskey='F' or @id='searchInput']  

//Using wildcard * with to finding element xpath
xpath=//*[@accesskey='F'] 

14. Finding nth child element of parent
//This xpath is for search text box. Here, 
// /*[3] describes the 3rd child element of body which is div[3].
//Same way *[2] describes the 2nd child element of fieldset which is input[2]

xpath=//body/*[3]/form/fieldset/*[2]  

Xpath Examples for drop down
1. xpath=//body/div[3]/form/fieldset/select
2. xpath=//body/div[3]/form/fieldset/select[last()]
3. xpath=//body/div[3]/form/fieldset/select[@id='searchLanguage']
4. xpath=//body/div[3]/form/fieldset/select[@name='language']
5. xpath=//div[@class='search-container']/descendant::select[@name='language']
6. xpath=//select[contains(@id, "searchLanguage")]
7. xpath=//div[@class='search-container']/descendant::select[position()=1]
8. xpath=//body/div[3]/form/fieldset/select[count(*)>1]

```


## CSSSelector

```java


(1) Id:
//div[@id='panel']



Class:
//div[@class='panelClass']

//div[@class='panelClass1 panelClass2']

Any Attributes:
//div[@name='continue']
//input[@type='button']

Direct Child:
//ul/li


Child or Subchild:
//ul//li

nth Child:
//ul[@id='drinks']/li[5]


Parent of an element:
//li[@class='blue']/..

Next Sibling:
//li[@class='blue']/../li[2]
//li[@class='blue']/../li[3]


Match by Innertext:
//a[contains(text(),'Sign in')]
//a[contains(string(),'Sign in')]

By Attribute
//a[contains(@id,’signup’)]
//a[contains(@id,’link-signup’)]
//a[contains(@id,’link)] 


(10) Match by Sub-string:

(i) Match a Sub-string(pattern):
//div[contains(@id,'pattern')]

(ii) Match a prefix:
//div[starts-with(@id,"prefixString")]

(iii) Match a suffix:
//div[ends-with(@id,"suffixString")]



contains()
//div[contains(@id,’module’)]
//*[@id=’regular-expression-syntax’]//h2[contains(text(), ‘7.2.1. Regular Expression Syntax’)]

concat()
concat(//*[@id=’checking-for-a-pair’]/h3/text(), //*[@id=’simulating-scanf’]/h3/text())

normalize-space()
//*[@id=’sb_form_q’][normalize-space(@value)=’asd asd’]

starts-with()
//div[starts-with(@id,’module’)]
string-length()
The string-length returns the number of characters in the string
string-length(//*[@id=’regular-expression-syntax’]/h2/text())

substring()
substring(//*[@id=’regular-expression-syntax’]/h2/text(), 2, 30)

substring-after()
//div[substring-after(@id,’finding-‘)]
//*[starts-with(@id,’finding’) and substring-after(@id,’finding-all-adverbs-‘)]

substring-before()
//div[substring-before(@id,’objects’)]
ancestor
Ancestor lets you select any ancestors [e.g., Parent and Grandparent] of the current node.
//*[@id=’regular-expression-syntax’]/ancestor::div[5]/div[2]
//*[@id=’regular-expression-syntax’]/ancestor::*

ancestor-or-self
Ancestor-or-self lets you select any ancestors [e.g., Parent and Grandparent] of the current node including the current node.
//*[@id=’regular-expression-syntax’]/ancestor-or-self::div[1]
//*[@id=’regular-expression-syntax’]/ancestor-or-self::*

attribute
Attribute returns all the attributes in the current node.
//*[@class=’sphinxsidebarwrapper’]/attribute::*
//*[@id=’sidebarbutton’]/attribute::title

child
Child returns all the children in the current node.
//*[@class=’sphinxsidebarwrapper’]/child::*
//*//child::h3

descendant
Descendant lets you select all descendants [e.g., Children and Grandchildren] of the current node.
//*[@class=’this-page-menu’]/descendant::*
//*[@class=’this-page-menu’]/descendant::li[2]
//*[@class=’documentwrapper’]/descendant::div[position()=3]

descendant-or-self
Descendant-or-self lets you select all descendants [e.g., Children and Grandchildren] of the current node including the current node.
//*[@class=’this-page-menu’]/descendant-or-self::*
//*[@id=’searchbox’]/descendant-or-self::form[@class=’search’]/input[2]

following
Following returns all in the document after the closing tag of the current node.
//*[@class=’clearer’]/following::*

following-sibling
Following-sibling returns all the sibling after the closing tag of the current node.
//*[@class=’related’]/following-sibling::*
//*[@class=’related’]/following-sibling::div[3]

//Absolute XPath
web_element_name=html/body/div[30]/div[2]/div[2]/div/div/div/div[1]/table/tbody/tr/td[1]/table/tbody/tr[2]/td[2]/em/button
 

WebElement userName = driver.findElement(By.cssSelector("html body div div form input"));
WebElement userName = driver.findElement(By.cssSelector("input"));
WebElement userName = driver.findElement(By.cssSelector("div > a"));
WebElement userName = driver.findElement(By.cssSelector("div a"));
WebElement userName = driver.findElement(By.cssSelector("input#username"));


WebElement userName = driver.findElement(By.cssSelector("#username"));
WebElement userName = driver.findElement(By.cssSelector("input.classname"));


WebElement userName = driver.findElement(By.cssSelector(".classname"));
WebElement previousButton = driver.findElement(By.cssSelector("img[alt='Previous']"));
List<WebElement> imagesWithAlt = driver.findElements(By.cssSelector("img[alt]"));
WebElement previousButton = driver.findElement(By.cssSelector("header[id^='page-']"));
WebElement previousButton = driver.findElement(By.cssSelector("header[id$='page-']"));
WebElement previousButton = driver.findElement(By.cssSelector("header[id*='page-']"));  





WebElement userName = driver.findElement(By.xpath("html/body/div/div/form/input"));
WebElement userName = driver.findElement(By.xpath("//input"));
WebElement userName = driver.findElement(By.xpath("//div/a"));
WebElement userName = driver.findElement(By.xpath("//div//a"));
WebElement userName = driver.findElement(By.xpath(".//*[text()='Первая ссылка']/.."));
WebElement userName = driver.findElement(By.xpath("//input[@id='username']"));
List<WebElement> imagesWithAlt = driver.findElements(By.xpath ("img[@alt]"));
WebElement userName = driver.findElement(By.xpath("//input[@id='username']/.."));


//Css Selector Using ID Selector
var TxtBoxElement = driver.FindElement(By.CssSelector("input#userid"));

//Css Selector Using Class Selector
var TxtBoxElement = driver.FindElement(By.CssSelector("input.txtuser"));

WebElement cssele = driver.findElements(By.cssSelector("input.textboxcss.top"));


//Css Selector Using Attributes Selector
var TxtBoxElement = driver.FindElement(By.CssSelector("input[id=userid]"));
var BtnElement = driver.FindElement(By.CssSelector("button[class=btnclass]"));
var AnchorElement = driver.FindElement(By.CssSelector("a[title=myLink]"));
WebElement cssele = driver.findElements(By.cssSelector("input#txtName[name=’taComment’]"));

//Tag, Class and Attribute

WebElement cssele = driver.findElements(By.cssSelector("input.textboxcss [name=’taComment’]"));

//Css Selector Using Pattern Matching
//1. Starts With (prefix)
var TxtBoxElement = driver.FindElement(By.CssSelector("input[id^='user']"));

//2. Ends With (suffix)
var BtnElement = driver.FindElement(By.CssSelector("button[class$='btn']"));

//3. Contains
var AnchorElement = driver.FindElement(By.CssSelector("a[href*='yahoo'] "));


//CSS Selector using Parent (indirect child)
var ElementA = driver.FindElement(By.CssSelector("div#parentdiv input.txtclass]"));
var ElementB = driver.FindElement(By.CssSelector("div#parentdiv id=anchor]"));


//CSS Selector using Parent (direct child)
var ElementA = driver.FindElement(By.CssSelector("div#parentdiv > input.txtclass]"));
var ElementB = driver.FindElement(By.CssSelector("div#parentdiv  > id=anchor]")


//nth-chilld()
WebElement cssele = driver.findElements(By.cssSelector("li:nth-child(n)"));

//Inner text
WebElement cssele = driver.findElements(By.cssSelector("span:contains(‘Upload you pic‘)"));


WebElement ele1 = driver.findElement(By.cssSelector(".primary-btn"));
WebElement ele2 = driver.findElement(By.cssSelector("btn.primary-btn"));
WebElement ele3 = driver.findElement(By.cssSelector("btn.primary-btn"));  

WebElement Email = driver.findElement(By.cssSelector("input[id=email]"));

driver.FindElement(By.CssSelector("#rightbar > .menu > li:nth-of-type(3) > h5"));


IList<IWebElement> hotBanners = driver.FindElements(By.CssSelector(".ban.hot"));
IWebElement banUsStates = hotBanners[3];


driver.findElement(By.cssSelector(“input[id=’Email’]”)).sendKeys(“abcd”);
driver.findElement(By.cssSelector(“input[name=’Passwd’]”)).sendKeys(“Rahul”);

//using multiple attributes
//driver.findElement(By.cssSelector(“input[id=’signIn’][value=’Sign in’]”)).click();

//using class name: 2 special chars. . for class and # for id

//driver.findElement(By.cssSelector(“input.rc-button”)).click();

//using multiple classes
//driver.findElement(By.cssSelector(“input.rc-button.rc-button-submit”)).click();

//using #
//driver.findElement(By.cssSelector(“input#signIn”)).click();

//^=start with $=ends with *=contains

/*driver.findElement(By.cssSelector(“input[id^=’Em’]”)).sendKeys(“abcd”);

driver.findElement(By.cssSelector(“input[id$=’wd’]”)).sendKeys(“abcd”);

driver.findElement(By.cssSelector(“input[value*=’n i’]”)).click();*/

driver.findElement(By.cssSelector(“css=a:contains(‘Sign in’)”)).click();


1. Selenium CSS locator using Tag and any Attribute
css=input[type=search] \\\\ This syntax will find "input" tag node which contains "type=search" attribute.

css=input[id=searchInput] \\\\ This syntax will find "input" tag node which contains "id=searchInput" attribute.

css=form input[id=searchInput]  \\\\  This syntax will find form containing "input" tag node which contains "id=searchInput" attribute.

(All three CSS path examples given above will locate Search text box.)

2. Selenium CSS locator using Tag and ID attribute
css=input#searchInput \\\\ Here, '#' sign is specially used for "id" attribute only. It will find "input" tag node which contains "id=searchInput" attribute. This syntax will locate Search text box.

3. Selenium CSS locator using Tag and class attribute
css=input.formBtn  \\\\  Here, '.' is specially used for "class" attribute only. It will find "input" tag node which contains "class=formBtn" attribute. This syntax will locate Search button (go).

4.  Selenium CSS locator using tag, class, and any attribute
css=input.formBtn[name=go]  \\\\ It will find "input" tag node which contains "class=formBtn" class and "name=go" attribute. This syntax will locate Search button (go).

5. Tag and multiple Attribute CSS locator
css=input[type=search][name=search] \\\\  It will find "input" tag node which contains "type=search" attribute and "name=search" attribute. This syntax will locate Search text box.

6. CSS Locator using Sub-string matches(Start, end and containing text) in selenium
css=input[id^='search']  \\\\  It will find input node which contains 'id' attribute starting with 'search' text.(Here, ^ describes the starting text).

css=input[id$='chInput']  \\\\  It will find input node which contains 'id' attribute starting with 'chInput' text. (Here, $ describes the ending text).

css=input[id*='archIn']  \\\\  It will find input node which contains 'id' attribute containing 'archIn' text. (Here, * describes the containing text).

(All three CSS path examples given above will locate Search text box on page of software web application.)

7. CSS Element locator syntax using child Selectors
css=div.search-container>form>fieldset>input[id=searchInput]  \\\\  First it will find div tag with "class = search-container" and then it will follow remaining path to locate child node. This syntax will locate Search text box.

8. CSS Element locator syntax using adjacent selectors
css=input + input  \\\\  It will locate "input" node where another "input" node is present before it on page.(for search tect box).

css=input + select or css=input + input + select \\\\  It will locate "select" node, where "input" node is present before it on page(for language drop down).

9. CSS Element locator using contains keyword
css=strong:contains("English")  \\\\ It will looks for the element containing text "English" as a value on the page.




```



## Navigation

```java

driver.get("http://www.google.com");

driver.navigate().to("http://www.google.com");

driver.navigate().refresh();

//Go back to the last visited page
driver.navigate().back();

//go forward to the next page
driver.navigate().forward();

```

## Navigation
```java

//getCookies
driver.get("https://www.google.co.in");
Set<Cookie> cookies = driver.manage().getCookies();
for(Cookie ck :cookies) {
	System.out.println(ck);
}

//getCookieNamed
System.out.println(driver.manage().getCookieNamed("lastloggin"));

//addCookie
Cookie cookie = new Cookie("lastloggin", "10/10/2015");
driver.manage().addCookie(cookie);

//deleteCookie
driver.get("https://www.google.co.in");
Set<Cookie> cookies = driver.manage().getCookies();
for(Cookie ck :cookies) {
	driver.manage().deleteCookie(ck);
}

//deleteAllCookies
driver.manage().deleteAllCookies();

//deleteCookieNamed
driver.manage().deleteCookieNamed("lastloggin");
```

## Waiting

```java
WebDriverWait wait = new WebDriverWait(driver, 30);
WebElement element = wait.until(ExpectedConditions.elementToBeClickable(By.id("id123")));

//presenceOfElementLocated - Verify presence of element in the DOM.
WebDriverWait wait = new WebDriverWait(driver, 1000);
wait.until(ExpectedConditions.presenceOfElementLocated(By.linkText("QAmail"))); 

//Using elementToBeClickable
wait.until(ExpectedConditions.elementToBeClickable(By.linkText("TGmail")));

//c. Using invisibilityOfElementLocated
wait.until(ExpectedConditions.invisibilityOfElementLocated(By.linkText("tGmail")));

//invisibilityOfElementWithText - Validating the invisibility of element with text for the element provided.
wait.until(ExpectedConditions.invisibilityOfElementWithText(By.xpath("//div[@id='_eE']"), "tGmail")); 

//textToBePresentInElement - Validating the text to be present in the element defined by locator.
wait.until(ExpectedConditions.textToBePresentInElement(By.xpath("//div[@id='_eE']"),"Gmail")); 

//visibilityOfElementLocated by locator.
wait.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("//div[@id='_eE']"))); 

//titleContains - Wait until the title is displayed correctly
wait.until(ExpectedConditions.titleContains("QA Automation QTP"));

// alertIsPresent - waits for alert to appear in the window.
wait.until(ExpectedConditions.alertIsPresent());


driver.manage().timeouts().implicitlyWait(15, TimeUnit.SECONDS); 


//How to wait till element visible or appear or present on page 
WebDriverWait wait = new WebDriverWait(driver, 15); 
wait.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("//input[@id='text3']")));



//How to apply wait in webdriver till element becomes invisible or hidden 
WebDriverWait wait = new WebDriverWait(driver, 15); 
wait.until(ExpectedConditions.invisibilityOfElementLocated(By.xpath("//input[@id='text4']"))); 


//Selenium WebDriver wait for title with example
WebDriverWait wait = new WebDriverWait(driver, 15); 
wait.until(ExpectedConditions.titleContains(": MyTest"));

//how to wait for alert in selenium
WebDriverWait wait = new WebDriverWait(driver, 15); 
wait.until(ExpectedConditions.alertIsPresent());


//wait for text to be present with example using explicit wait 
WebDriverWait wait = new WebDriverWait(driver, 15); 
wait.until(ExpectedConditions.textToBePresentInElementLocated(By.xpath("//div[@id='timeLeft']"), "Time left: 7 seconds")); 


//How to wait for element to be clickable in selenium webdriver using explicit wait
WebDriverWait wait = new WebDriverWait(driver, 15); 
wait.until(ExpectedConditions.elementToBeClickable(By.cssSelector("#submitButton"))); 

```

## Timeouts
```java
//implicitlyWait
driver.manage().timeouts().implicitlyWait(30, TimeUnit.DAYS); 
driver.manage().timeouts().implicitlyWait(30, TimeUnit.HOURS); 
driver.manage().timeouts().implicitlyWait(30, TimeUnit. MICROSECONDS); 
driver.manage().timeouts().implicitlyWait(30, TimeUnit. MILLISECONDS); 
driver.manage().timeouts().implicitlyWait(30, TimeUnit.MINUTES); 
driver.manage().timeouts().implicitlyWait(30, TimeUnit. NANOSECONDS); 
driver.manage().timeouts().implicitlyWait(30, TimeUnit.SECONDS);

//pageLoadTimeout
driver.manage().timeouts().pageLoadTimeout(3, TimeUnit.SECONDS); 

//setScriptTimeout
driver.manage().timeouts().setScriptTimeout(3, TimeUnit.SECONDS); 

```


##Keyboard Interaction
```java

// Configure the Action
Actions action = new Actions(driver);

// To click on the element
action.moveToElement(element).click().perform();


//Multiple Actions
Actions action = new Actions(driver);
action.movetoElement("webelement")
.click()
.sendkey("aaa")
.doubleClick("webelement")
.contextClick()
.keyDown(Keys.Down)
.build()
.perform()



//build
Actions action = new Actions(driver);
action.click(driver.findElement(By.locatorType("path")));
action.build();

//click
action.click(); 
action.click(driver.findElement(By.locatorType("path")));

//perform
driver.get("http://www.google.com");
Actions action = new Actions(driver);
action.click().build().perform();
or
action.click(driver.findElement(By.id("gsri_ok0"))).build().perform();

//doubleClick
action.doubleClick(ele).build().perform();

// contextClick
driver.get("http://docs.seleniumhq.org"); 
Actions action = new Actions(driver); 
WebElement ele = driver.findElement(By.xpath("//div[@ id='mainContent']/p[1]/i")); 
action.moveToElement(ele).contextClick().build().perform(); 


//clickAndHold
action.clickAndHold().build().perform();
action.clickAndHold(driver.findElement(By.locatorType("path"))).build().perform();

//moveToElement
Actions action = new Actions(driver);
WebElement source = driver.findElement(By.locatorType("path"));
action.moveToElement(source).build().perform();
action.moveToElement(source, 234, 345).build().perform();

//moveByOffset
Actions action = new Actions(driver);
action.moveByOffset(234, 345).build().perform();

//dragAndDrop
Actions action = new Actions(driver); 
WebElement source = driver.findElement(By.locatorType("path")); 
WebElement target = driver.findElement(By.locatorType("path")); 
action.dragAndDrop(source, target).build().perform(); 

//dragAndDropBy
Actions action = new Actions(driver); 
WebElement source = driver.findElement(By.locatorType("path")); 
action.dragAndDropBy(source, 456, 234).build().perform(); 


//keyDown
Actions action = new Actions(driver);
WebElement source = driver.findElement(By.locatorType("path"));
WebElement target = driver.findElement(By.locatorType("path"));
action.keyDown(Keys.CONTROL);
action.click(source);
action.click(target);
action.keyUp(Keys.CONTROL);
action.perform();


//keyUp
Actions action = new Actions(driver);
action.keyDown(Keys.CONTROL).sendKeys(Keys.END).keyUp(Keys.CONTROL).build().perform();


//Drag and Drop
WebElement source = driver.findElement(By.locatorType("path"));
WebElement target = driver.findElement(By.locatorType("path"));
Actions action = new Actions(driver);
Action dragAndDrop = action.clickAndHold(source)
.moveToElement(target)
.release(target Element)
.build();
dragAndDrop.perform();

public void dragAndDrop() throws AWTException, InterruptedException {
	driver.get("http://demo.kaazing.com/forex/");
	Actions action = new Actions(driver);
	WebElement sourceElement = driver.findElement(By.	xpath("(//li[@name='dragSource'])[13]"));
	Action drag = action.clickAndHold(sourceElement).build();
	drag.perform();
	WebElement targetElement = driver.findElement(By.	xpath("//section[@id='section1']/div[2]"));
	Point coordinates = targetElement.getLocation();
	Robot robot = new Robot(); //Robot for controlling mouse	actions
	robot.mouseMove(coordinates.getX(), coordinates.getY() + 120);
	Thread.sleep(2000);
	robot.mouseMove(coordinates.getX(), coordinates.getY() + 	110);
	Thread.sleep(5000);
}

//dragAndDropBy
Actions action = new Actions(driver);
WebElement source = driver.findElement(By.locatorType("path"));
action.dragAndDropBy(source, 456, 234).build().perform();


//release
WebElement source = driver.findElement(By.locatorType("path"));
WebElement target = driver.findElement(By.locatorType("path"));
Action dragAndDrop = action.clickAndHold(source)
.moveToElement(target)
.release(target)
.build();
dragAndDrop.perform();


//sendKeys
Actions action = new Actions(driver);
WebElement target = driver.findElement(By.locatorType("path"));
action.sendKeys(Keys.TAB).build().perform();
action.sendKeys(Keys.CONTROL, Keys.END).build().perform();
action.sendKeys(target, Keys.TAB).build().perform();

//Zoom In:
WebElement html = driver.findElement(By.tagName("html")); // WINDOWS
html.sendKeys(Keys.chord(Keys.CONTROL, Keys.ADD)); // MAC
html.sendKeys(Keys.chord(Keys.COMMAND, Keys.ADD));

//Zoom Out
WebElement html = driver.findElement(By.tagName("html")); // WINDOWS
html.sendKeys(Keys.chord(Keys.CONTROL, Keys.SUBTRACT)); // MAC
html.sendKeys(Keys.chord(Keys.COMMAND, Keys.SUBTRACT));

//Zoom 100%:
WebElement html = driver.findElement(By.tagName("html")); // WINDOWS
html.sendKeys(Keys.chord(Keys.CONTROL, "0")); // MAC
html.sendKeys(Keys.chord(Keys.COMMAND, Keys."0"));

//Enter:
driver.findElement(By.locatorType("path")).sendKeys(Keys.RETURN);
driver.findElement(By.locatorType("path")).sendKeys(Keys.ENTER);

//Mouse Hover
Actions action = new Actions(driver);
WebElement HoverLink = driver.findElement(By.linkText("value"));
action.moveToElement(HoverLink);
action.perform();




```

##Mouse Interaction
```java

```

##Take A Screenshot On The Page
```java
File snapshot =((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE);
```

##Execute A JavaScript
```java
JavascriptExecutor js = (JavascriptExecutor) driver;
String js = "document.getElementsByName('fillname')[0].value='Selvi'";
js.executeScript(js);


private static void addJQuery (JavascriptExecutor js) {

    String script = "";

    boolean needInjection = (Boolean)(js.executeScript("return this.$ === undefined;"));
    if(needInjection) {
        URL u = Resources.getResource("jquery.js");
        try {
            script = Resources.toString(u, Charsets.UTF_8);
        } catch(IOException e) {
            e.printStackTrace();
        }
        js.executeScript(script);
    }
}



WebElement element = (WebElement) js.executeScript("return jQuery.find('#hplogo');");



```

Upload A File 
```java
this.driver.Navigate().GoToUrl(
        @"https://demos.telerik.com/aspnet-ajax/ajaxpanel/application-scenarios/file-upload/defaultcs.aspx");
WebElement element = driver.FindElement(By.Id("ctl00_ContentPlaceholder1_RadUpload1file0"));
String filePath = @"D:\Projects\PatternsInAutomation.Tests\WebDriver.Series.Tests\bin\Debug\WebDriver.xml";
element.SendKeys(filePath);
```


##Scroll Up, Down Or Anywhere On A Page
```java
JavascriptExecutor jsx = (JavascriptExecutor) driver;
//Vertical scroll - down by 100 pixels
jsx.executeScript("window.scrollBy(0,100)", "");
//Vertical scroll - up by 55 pixels (note the number is minus 55)
jsx.executeScript("window.scrollBy(0,-55)", "");
//Horizontal scroll - right by 20 pixels
jsx.executeScript("window.scrollBy(20,0)", "");
//Horizontal scroll - left by 95 pixels (note the number is minus 95)
jsx.executeScript("window.scrollBy(-95,0)", "");


//Drag and Drop
this.driver.Navigate().GoToUrl(@"http://loopj.com/jquery-simple-slider/");
WebElement element = driver.FindElement(By.XPath("//*[@id='project']/p[1]/div/div[2]"));
Actions move = new Actions(driver);
move.DragAndDropToOffset(element, 30, 0).Perform();

```




```java
import org.openqa.Selenium.Proxy

FirefoxProfile profile = new FirefoxProfile();
String PROXY = "999.999.999.999:9999";
Proxy proxy = new Proxy();
proxy.HttpProxy=PROXY;
proxy.FtpProxy=PROXY;
proxy.SslProxy=PROXY;
profile.SetProxyPreferences(proxy);
FirefoxDriver driver = new FirefoxDriver(profile);
```




20. File Download

```java
FirefoxProfile Prof = new FirefoxProfile();
Prof.setPreference("browser.download.dir", "D:\\java prj");
Prof.setPreference("browser.download.folderList", 2);
Prof.setPreference("browser.helperApps.neverAsk.saveToDisk","application/zip");
  
WebDriver driver = new FirefoxDriver(Prof);
driver.get("http://seleniumhq.org/download/");
driver.manage().timeouts().implicitlyWait(3,TimeUnit.MINUTES);
driver.findElement(By.xpath("//a[@name='client-drivers']/table/tbody/tr[1]/td[4]/a")).click();
```

## Handle Alerts 

```java

**Import org.openqa.selenium.Alert**

WebDriverWait wait = new WebDriverWait(driver, 2);
wait.until(ExpectedConditions.alertIsPresent());

//Switch to Alert
Driver.switchTo().alert();

//Object Creation for Alert class
Alert alert = driver.switchTo().alert();
alert.getText();

//Accept the Alert
alert.accept();   

//Reject the Alert
alert.dismiss();

//authenticateUsing
UserAndPassword user = new UserAndPassword("USERNAME", "PASSWORD");
alert.authenticateUsing(user);

WebDriverWait wait = new WebDriverWait(driver, 10);
Alert alert = wait.until(ExpectedConditions.alertIsPresent());
alert.authenticateUsing(new UserAndPassword("USERNAME", "PASSWORD"));
Actions action = new Actions(driver);



```


##IFrames

```java
//By finding all the web elements using iframe tag
List<WebElement> iframeElements = driver.findElements(By.tagName("iframe"));
System.out.println("The total number of iframes are " + iframeElements.size());
		
//Switch by frame ID
driver.switchTo().frame("IFRAMEGOOGLEADID");
		
//Switch by Index
driver.switchTo().frame(0);

//Switch by frame name
driver.switchTo().frame("iframename");
		
//Switch to Frame by WebElement
driver.switchTo().frame(driver.findElement(By.id("IFRAMEGOOGLEADID")));

//Switching back to Main page from Frame
driver.switchTo().frame(0);
driver.switchTo().defaultContent();

//Wwitch to the parent frame and then switch to the child frame
driver.switchTo().frame("ParentFrame").switchTo().frame("ChildFrame");
```


## Window Handle

```java

//maximize
driver.manage().window().maximize();

//getSize
driver.manage().window().getSize();

//getPosition
System.out.println(driver.manage().window().getPosition());
System.out.println("Position X: " + driver.manage().window().getPosition().x);
System.out.println("Position Y: " + driver.manage().window().getPosition().y);
System.out.println("Position X: " + driver.manage().window().getPosition().getX());
System.out.println("Position Y: " + driver.manage().window().getPosition().getY());

//setSize
Dimension d = new Dimension(320, 480);
driver.manage().window().setSize(d);
driver.manage().window().setSize(new Dimension(320, 480));

//setPosition
Point p = new Point(200, 200);
driver.manage().window().setPosition(p);
driver.manage().window().setPosition(new Point(300, 150));

//getWindowHandle
String parentwindow = driver.getWindowHandle();
driver.switchTo().window(parentwindow);

//getWindowHandles
Set<String> childwindows = driver.getWindowHandles();
driver.SwitchTo().Window(childwindow);
driver.close();
driver.SwitchTo().Window(parentWindow);



//Return a string of alphanumeric window handle
String  handle= driver.getWindowHandle();

//get the window handle of all the current windows
Set<String> windows = driver.getWindowHandles();
Iterator<String> itr = windows.iterator();

//loop thru 
for (String handle : driver.getWindowHandles()) {
    driver.switchTo().window(handle);}
}




//patName will provide you parent window
String patName = itr.next();

//chldName will provide you child window
String chldName = itr.next();

//Switch to child window
driver.switchto().window(chldName);

handles.remove(chldName);

//Do normal selenium code for performing action in child window

//To come back to parent window
driver.switchto().window(patName);



//To close all the other windows except the main window.
public static boolean closeAllOtherWindows(String openWindowHandle) {
	Set<String> allWindowHandles = driver.getWindowHandles();
	for (String currentWindowHandle : allWindowHandles) {
		if (!currentWindowHandle.equals(openWindowHandle)) {
			driver.switchTo().window(currentWindowHandle);
			driver.close();
		}
	}
	
	driver.switchTo().window(openWindowHandle);
	if (driver.getWindowHandles().size() == 1)
		return true;
	else
		return false;
}
```


## Window Handle


```java
//Implicitly Wait Command
driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);


//Explicit Wait Command
WebDriverWait wait = new WebDriverWait(driver, 10);
WebElement element = wait.until(ExpectedConditions.elementToBeClickable(By.id(>someid>)));

//PageLoadTimeout Command
driver.manage().timeouts().pageLoadTimeout(100, SECONDS);

//SetScriptTimeout Command
driver.manage().timeouts().setScriptTimeout(100,SECONDS);

//Sleep Command
thread.sleep(1000)

```


alertIsPresent() : Is Alert Present?
elementSelectionStateToBe: Is the element selected?
elementToBeClickable: Is the element clickable?
elementToBeSelected: Element is selected
frameToBeAvailableAndSwitchToIt: Is frame available and selected?
invisibilityOfElementLocated: Is the element invisible?
presenceOfAllElementsLocatedBy: All elements presence location.
refreshed: Wait for a page refresh.
textToBePresentInElement: Is the text present for a particular element?
textToBePresentInElementValue: Is the element value present for a particular element?
visibilityOf: Is the element visible?
titleContains: Is that title contain?



//Handle browser based authentication using Selenium Webdriver
driver.get("http://username:password@selvi.com/");


```java

//Switch Between Browser Windows or Tabs

 this.driver.Navigate().GoToUrl(@"http://automatetheplanet.com/compelling-sunday-14022016/");
    driver.FindElement(By.LinkText("10 Advanced WebDriver Tips and Tricks Part 1")).Click();
    driver.FindElement(By.LinkText("The Ultimate Guide To Unit Testing in ASP.NET MVC")).Click();
    ReadOnlyCollection<String> windowHandles = driver.WindowHandles;
    String firstTab = windowHandles.First();
    String lastTab = windowHandles.Last();
    driver.SwitchTo().Window(lastTab);
    Assert.AreEqual<string>("The Ultimate Guide To Unit Testing in ASP.NET MVC", driver.Title);
    driver.SwitchTo().Window(firstTab);
    Assert.AreEqual<string>("Compelling Sunday – 19 Posts on Programming and Quality Assurance", driver.Title);


//Navigation History
this.driver.Navigate().GoToUrl(
        @"http://www.codeproject.com/Articles/1078541/Advanced-WebDriver-Tips-and-Tricks-Part");
    this.driver.Navigate().GoToUrl(
        @"http://www.codeproject.com/Articles/1017816/Speed-up-Selenium-Tests-through-RAM-Facts-and-Myth");
    driver.Navigate().Back();
    Assert.AreEqual<string>(
        "10 Advanced WebDriver Tips and Tricks - Part 1 - CodeProject", 
        driver.Title);
    driver.Navigate().Refresh();
    Assert.AreEqual<string>(
        "10 Advanced WebDriver Tips and Tricks - Part 1 - CodeProject", 
        driver.Title);
    driver.Navigate().Forward();
    Assert.AreEqual<string>(
        "Speed up Selenium Tests through RAM Facts and Myths - CodeProject", 
        driver.Title);


//Change User Agent

FirefoxProfileManager profileManager = new FirefoxProfileManager();
FirefoxProfile profile = new FirefoxProfile();
profile.SetPreference(
"general.useragent.override",
"Mozilla/5.0 (BlackBerry; U; BlackBerry 9900; en) AppleWebKit/534.11+ (KHTML, like Gecko) Version/7.1.0.346 Mobile Safari/534.11+");
this.driver = new FirefoxDriver(profile);




//Set HTTP Proxy for Browser

FirefoxProfile firefoxProfile = new FirefoxProfile();
firefoxProfile.SetPreference("network.proxy.type", 1);
firefoxProfile.SetPreference("network.proxy.http", "myproxy.com");
firefoxProfile.SetPreference("network.proxy.http_port", 3239);
driver = new FirefoxDriver(firefoxProfile);


Handle SSL Certificate Error

//Handle SSL Certificate Error FirefoxDriver
FirefoxProfile firefoxProfile = new FirefoxProfile();
firefoxProfile.AcceptUntrustedCertificates = true;
firefoxProfile.AssumeUntrustedCertificateIssuer = false;
driver = new FirefoxDriver(firefoxProfile);


//Handle SSL Certificate Error ChromeDriver
DesiredCapabilities capability = DesiredCapabilities.Chrome();
Environment.SetEnvironmentVariable("webdriver.chrome.driver", "C:\\Path\\To\\ChromeDriver.exe");
capability.SetCapability(CapabilityType.AcceptSslCertificates, true);
driver = new RemoteWebDriver(capability);


//Handle SSL Certificate Error InternetExplorerDriver

DesiredCapabilities capability = DesiredCapabilities.InternetExplorer();
Environment.SetEnvironmentVariable("webdriver.ie.driver", "C:\\Path\\To\\IEDriver.exe");
capability.SetCapability(CapabilityType.AcceptSslCertificates, true);
driver = new RemoteWebDriver(capability);



//Scroll Focus to Control
this.driver.Navigate().GoToUrl(@"http://automatetheplanet.com/compelling-sunday-14022016/");
    IWebElement link = driver.FindElement(By.PartialLinkText("Previous post"));
    string jsToBeExecuted = string.Format("window.scroll(0, {0});", link.Location.Y);
    ((IJavaScriptExecutor)driver).ExecuteScript(jsToBeExecuted);
    link.Click();
    Assert.AreEqual<string>("10 Advanced WebDriver Tips and Tricks - Part 1", driver.Title);


//Focus on a Control

this.driver.Navigate().GoToUrl(
    @"http://automatetheplanet.com/compelling-sunday-14022016/");
    IWebElement link = driver.FindElement(By.PartialLinkText("Previous post"));

    //Option 1.
    link.SendKeys(string.Empty);

    //Option 2.
    ((IJavaScriptExecutor)driver).ExecuteScript("arguments[0].focus();", link);




1. Taking a Screenshot
public void TakeFullScreenshot(IWebDriver driver, String filename)
{
    Screenshot screenshot = ((ITakesScreenshot)driver).GetScreenshot();
    screenshot.SaveAsFile(filename, ImageFormat.Png);
}


public void TakeScreenshotOfElement(IWebDriver driver, By by, string fileName)
{
    // 1. Make screenshot of all screen
    var screenshotDriver = driver as ITakesScreenshot;
    Screenshot screenshot = screenshotDriver.GetScreenshot();
    var bmpScreen = new Bitmap(new MemoryStream(screenshot.AsByteArray));

    // 2. Get screenshot of specific element
    IWebElement element = driver.FindElement(by);
    var cropArea = new Rectangle(element.Location, element.Size);
    var bitmap = bmpScreen.Clone(cropArea, bmpScreen.PixelFormat);
    bitmap.Save(fileName);
}


[TestMethod]
public void WebDriverAdvancedUsage_TakingFullScrenenScreenshot()
{
    this.driver.Navigate().GoToUrl(@"http://automatetheplanet.com");
    this.WaitUntilLoaded();
    string tempFilePath = Path.GetTempFileName().Replace(".tmp", ".png");
    this.TakeFullScreenshot(this.driver, tempFilePath);
}

[TestMethod]
public void WebDriverAdvancedUsage_TakingElementScreenshot()
{
    this.driver.Navigate().GoToUrl(@"http://automatetheplanet.com");
    this.WaitUntilLoaded();
    string tempFilePath = Path.GetTempFileName().Replace(".tmp", ".png");
    this.TakeScreenshotOfElement(this.driver, 
    By.XPath("//*[@id='tve_editor']/div[2]/div[2]/div/div"), tempFilePath);
}



//Execute JavaScript
 this.driver.Navigate().GoToUrl(@"http://automatetheplanet.com");
    this.WaitUntilLoaded();
    IJavaScriptExecutor js = driver as IJavaScriptExecutor;
    string title = (string)js.ExecuteScript("return document.title");
    Debug.WriteLine(title);



//Set Page Load Timeout
this.driver.Manage().Timeouts().SetPageLoadTimeout(new TimeSpan(0, 0, 10));


private void WaitUntilLoaded()
{
    WebDriverWait wait = new WebDriverWait(driver, TimeSpan.FromSeconds(30));
    wait.Until((x) =>
    {
        return ((IJavaScriptExecutor)this.driver)
        .ExecuteScript("return document.readyState").Equals("complete");
    });
}



WebDriverWait wait = new WebDriverWait(driver, TimeSpan.FromSeconds(30));
wait.Until(ExpectedConditions.VisibilityOfAllElementsLocatedBy(
  By.XPath("//*[@id='tve_editor']/div[2]/div[2]/div/div")));



Execute Tests in a Headless Browser


this.driver = new PhantomJSDriver(
        @"D:\Projects\PatternsInAutomation.Tests\WebDriver.Series.Tests\Drivers");
    this.driver.Navigate().GoToUrl(@"http://automatetheplanet.com");
    this.WaitUntilLoaded();
    IJavaScriptExecutor js = driver as IJavaScriptExecutor;
    string title = (string)js.ExecuteScript("return document.title");
    Debug.WriteLine(title);



Check If an Element Is Visible
Assert.IsTrue(driver.FindElement(
        By.XPath("//*[@id='tve_editor']/div[2]/div[2]/div/div")).Displayed);



Use Specific Profile
FirefoxProfileManager profileManager = new FirefoxProfileManager();
FirefoxProfile profile = profileManager.GetProfile("YourProfileName");
this.driver = new FirefoxDriver(profile);



ChromeOptions options = new ChromeOptions();
// set some options
DesiredCapabilities dc = DesiredCapabilities.Chrome();
dc.SetCapability(ChromeOptions.Capability, options);
IWebDriver driver = new RemoteWebDriver(dc);



Turn Off JavaScript
FirefoxProfileManager profileManager = new FirefoxProfileManager();
FirefoxProfile profile = profileManager.GetProfile("HARDDISKUSER");
profile.SetPreference("javascript.enabled", false);
this.driver = new FirefoxDriver(profile);



Manage Cookies


Cookie cookie = new Cookie("key", "value");
this.driver.Manage().Cookies.AddCookie(cookie);



Get All Cookies
var cookies = this.driver.Manage().Cookies.AllCookies;
foreach (var currentCookie in cookies)
{
    Debug.WriteLine(currentCookie.Value);
}


Delete a Cookie by Name
this.driver.Manage().Cookies.DeleteCookieNamed("CookieName");

Delete All Cookies
this.driver.Manage().Cookies.DeleteAllCookies();

Get a Cookie by Name
var myCookie = this.driver.Manage().Cookies.GetCookieNamed("CookieName");
Debug.WriteLine(myCookie.Value);


Maximize Window
driver.Manage().Window.Maximize();

```

## Select
```java
new Select(driver.findElement(By.id("gender"))).selectByVisibleText("Germany");


Select dropdown = new Select(driver.findElement(By.id("identifier")));
dropdown.selectByVisibleText("Programmer ");
dropdown.selectByIndex(1);
dropdown.selectByValue("prog");


WebElement select = driver.findElement(By.id("gender"));
List<WebElement> options = select.findElements(By.tagName("option"));



for (WebElement option : options) {

if("Germany".equals(option.getText().trim()))

 option.click();   
}



List<WebElement> list = sel.getOptions();
 for(int i=0;i<list.size();i++){
        if(list.get(i).getText().equals(sel.getFirstSelectedOption().getText())){
            System.out.println("The index of the selected option is: "+i);
            break;
            }


//checks whether the check box is selected or not. If it is not selected, then it selects.
if ( !driver.findElement(By.id("idOfTheElement")).isSelected() )
{
     driver.findElement(By.id("idOfTheElement")).click();
}


```

## Select
```java
//selectByIndex
driver.get("http://www.barnesandnoble.com/");
Select select = new Select(driver.findElement(By.id("quick-search-1-category")));
select.selectByIndex(1);
select.selectByIndex(2);

//selectByValue
driver.get("http://www.barnesandnoble.com/");
Select select = new Select(driver.findElement(By.id("quick-search-1-category")));
select.selectByValue("music");

//getFirstSelectedOption
driver.get("http://www.barnesandnoble.com/");
Select select = new Select(driver.findElement(By.id("quick-search-1-category")));
select.selectByIndex(6);
WebElement FSO = select.getFirstSelectedOption();
System.out.println(select.getFirstSelectedOption().getText());

//selectByVisibleText
driver.get("http://www.barnesandnoble.com/");
Select select = new Select(driver.findElement(By.id("quick-search-1-category")));
select.selectByVisibleText("Music");

//getAllSelectedOptions
driver.get("http://www.barnesandnoble.com/");
Select select = new Select(driver.findElement(By.id("quick-search-1-category")));
List<WebElement> selectedOptions = select.getAllSelectedOptions();
for(WebElement b : selectedOptions) {
	System.out.println(b.getText());
}

//getOptions
driver.get("http://www.barnesandnoble.com/");
Select select = new Select(driver.findElement(By.id("quick-search-1-category")));
for (WebElement b : select.getOptions()) {
	System.out.println(b.getText());
}

//isMultiple
driver.get("http://www.barnesandnoble.com/");
Select select = new Select(driver.findElement(By.id("quick-search-1-category")));
if(select.isMultiple()){
	System.out.println("Support multiple select at a time");
}
else{
	System.out.println("Doesn't support multiple select at a time");
}

//deselectAll
driver.get("http://compendiumdev.co.uk/selenium/basic_html_form.html");
Select select = new Select(driver.findElement(By.name("multipleselect[]")));
select.deselectAll();

//deselectByIndex
select.deselectByIndex(3);

//deselectByValue
select.deselectByValue("ms4");

//deselectByVisibleText
select.deselectByVisibleText("Selection Item 4");


```


## Select
```java



//Start FirefoxDriver with Plugins
FirefoxProfile profile = new FirefoxProfile();
profile.AddExtension(@"C:\extensionsLocation\extension.xpi");
IWebDriver driver = new FirefoxDriver(profile);



//Set HTTP Proxy ChromeDriver
ChromeOptions options = new ChromeOptions();
var proxy = new Proxy();
proxy.Kind = ProxyKind.Manual;
proxy.IsAutoDetect = false;
proxy.HttpProxy =
proxy.SslProxy = "127.0.0.1:3239";
options.Proxy = proxy;
options.AddArgument("ignore-certificate-errors");
IWebDriver driver = new ChromeDriver(options);


//Set HTTP Proxy with Authentication ChromeDriver
ChromeOptions options = new ChromeOptions();
var proxy = new Proxy();
proxy.Kind = ProxyKind.Manual;
proxy.IsAutoDetect = false;
proxy.HttpProxy =
proxy.SslProxy = "127.0.0.1:3239";
options.Proxy = proxy;
options.AddArguments("--proxy-server=http://user:password@127.0.0.1:3239");
options.AddArgument("ignore-certificate-errors");
IWebDriver driver = new ChromeDriver(options);


Start ChromeDriver with an Unpacked Extension
ChromeOptions options = new ChromeOptions();
options.AddArguments("load-extension=/pathTo/extension");
DesiredCapabilities capabilities = new DesiredCapabilities();
capabilities.SetCapability(ChromeOptions.Capability, options);
DesiredCapabilities dc = DesiredCapabilities.Chrome();
dc.SetCapability(ChromeOptions.Capability, options);
IWebDriver driver = new RemoteWebDriver(dc);


//Start ChromeDriver with an Packed Extension
ChromeOptions options = new ChromeOptions();
options.AddExtension(Path.GetFullPath("local/path/to/extension.crx"));
DesiredCapabilities capabilities = new DesiredCapabilities();
capabilities.SetCapability(ChromeOptions.Capability, options);
DesiredCapabilities dc = DesiredCapabilities.Chrome();
dc.SetCapability(ChromeOptions.Capability, options);
IWebDriver driver = new RemoteWebDriver(dc);


//Assert a Button Enabled or Disabled

IWebElement button = driver.FindElement(By.XPath("/html/body/button"));
Assert.IsFalse(button.Enabled);



//Set and Assert the Value of a Hidden Field
////<input type="hidden" name="country" value="Bulgaria"/>
    IWebElement theHiddenElem = driver.FindElement(By.Name("country"));
    string hiddenFieldValue = theHiddenElem.GetAttribute("value");
    Assert.AreEqual("Bulgaria", hiddenFieldValue);
    ((IJavaScriptExecutor)driver).ExecuteScript(
        "arguments[0].value='Germany';",
        theHiddenElem);
    hiddenFieldValue = theHiddenElem.GetAttribute("value");
    Assert.AreEqual("Germany", hiddenFieldValue);



//Wait AJAX Call to Complete Using JQuery

public void WaitForAjaxComplete(int maxSeconds)
{
    bool isAjaxCallComplete = false;
    for (int i = 1; i <= maxSeconds; i++)
    {
        isAjaxCallComplete = (bool)((IJavaScriptExecutor)driver).
        ExecuteScript("return window.jQuery != undefined && jQuery.active == 0");

        if (isAjaxCallComplete)
        {
            return;
        }
        Thread.Sleep(1000);
    }
    throw new Exception(string.Format("Timed out after {0} seconds", maxSeconds));
}



//Verify File Downloaded ChromeDriver
[TestMethod]
public void VerifyFileDownloadChrome()
{
    string expectedFilePath = @"c:\temp\Testing_Framework_2015_3_1314_2_Free.exe";
    try
    {
        String downloadFolderPath = @"c:\temp\";
        var options = new ChromeOptions();
        options.AddUserProfilePreference("download.default_directory", downloadFolderPath);
        driver = new ChromeDriver(options);

        driver.Navigate().GoToUrl("https://www.telerik.com/download-trial-file/v2/telerik-testing-framework");
        WebDriverWait wait = new WebDriverWait(driver, TimeSpan.FromSeconds(30));
        wait.Until((x) =>
        {
            return File.Exists(expectedFilePath);
        });
        FileInfo fileInfo = new FileInfo(expectedFilePath);
        long fileSize = fileInfo.Length;
        Assert.AreEqual(4326192, fileSize);
    }
    finally
    {
        if (File.Exists(expectedFilePath))
        {
            File.Delete(expectedFilePath);
        }
    }
}


//Verify File Downloaded FirefoxDriver
public void VerifyFileDownloadFirefox()
{
    string expectedFilePath = @"c:\temp\Testing_Framework_2015_3_1314_2_Free.exe";
    try
    {
        String downloadFolderPath = @"c:\temp\";
        FirefoxProfile profile = new FirefoxProfile();
        profile.SetPreference("browser.download.folderList", 2);
        profile.SetPreference("browser.download.dir", downloadFolderPath);
        profile.SetPreference("browser.download.manager.alertOnEXEOpen", false);
        profile.SetPreference("browser.helperApps.neverAsk.saveToDisk", "application/msword, application/binary, application/ris, text/csv, image/png, application/pdf, text/html, text/plain, application/zip, application/x-zip, application/x-zip-compressed, application/download, application/octet-stream");
        this.driver = new FirefoxDriver(profile);

        driver.Navigate().GoToUrl("https://www.telerik.com/download-trial-file/v2/telerik-testing-framework");
        WebDriverWait wait = new WebDriverWait(driver, TimeSpan.FromSeconds(30));
        wait.Until((x) =>
        {
            return File.Exists(expectedFilePath);
        });
        FileInfo fileInfo = new FileInfo(expectedFilePath);
        long fileSize = fileInfo.Length;
        Assert.AreEqual(4326192, fileSize);
    }
    finally
    {
        if (File.Exists(expectedFilePath))
        {
            File.Delete(expectedFilePath);
        }
    }
}
```


## Switching user agents 
```java
System.setProperty("webdriver.chrome.driver","C:\\chromedriver.exe"); 
ChromeOptions options = new ChromeOptions(); 
options.addArguments("user-data-dir=C:/Users/user_name/AppData/Local/ Google/Chrome/User Data"); 
options.addArguments("--user-agent=Mozilla/5.0 (iPhone; U; CPU iPhone OS 4_3_2 like Mac OS X; en-us) AppleWebKit/533.17.9 (KHTML, like Gecko) Version/5.0.2 Mobile/8H7 Safari/6533.18.5"); //iPhone 4 
options.addArguments("--start-maximized"); 
driver = new ChromeDriver(options); 
```

## License


## Links		
* [Automate Telerik Kendo Grid Webdriver](http://automatetheplanet.com/automate-telerik-kendo-grid-webdriver/)




