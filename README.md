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
- [Find Elements](#find-elements)    
* [Simple Testcase](simple-testcase)
* [Find Elements](find-elements)
* [Xpath](xpath)
* [CSS Selector](cssselector)
* [Navigation](navigation)
* [Cookies](cookies)
* [Waiting](waiting)
* [Keyboard Interaction](keyboard-interaction)
* [Mouse Interaction](mouse-interaction)
* [Take a screenshot](take-a-screenshot-on-the-page)
* [Execute Javascript](execute-a-javascript)
* [Upload file](upload-a-file)
* [Scroll](scroll-up-down-or-anywhere-on-a-page)
* [Setting Proxy in Firefox](setting-proxy-in-firefox)
* [Handle Alerts](handle-alerts)
* [iFrames](iframes)
* [Window Hhandle](window-handle)
* [Select](select)
* [assert-a-button-enabled-or-disabled](assert-a-button-enabled-or-disabled)


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

## Cookies
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
WebElement element = wait.until(ExpectedConditions.elementToBeClickable(By.id("element_id123")));

//Sleep Command
thread.sleep(1000)

//implicitlyWait
driver.manage().timeouts().implicitlyWait(15, TimeUnit.SECONDS);

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

```

##Mouse Interaction
```java

WebElement source = driver.findElement(By.locatorType("path"));
WebElement target = driver.findElement(By.locatorType("path"));
Action dragAndDrop = action.clickAndHold(source)
.moveToElement(target)
.release(target)
.build();
dragAndDrop.perform();

```

##Take A Screenshot On The Page
```java
File snapshot =((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE);
snapshot.SaveAsFile(filename, ImageFormat.Png);
```

## Execute A JavaScript
```java
JavascriptExecutor js = (JavascriptExecutor) driver;
String js = "document.getElementsByName('fillname')[0].value='Selvi'";
js.executeScript(js);

```

## Upload A File 
```java

this.driver.get("https://demos.telerik.com/aspnet-ajax/ajaxpanel/application-scenarios/file-upload/defaultcs.aspx");
WebElement element = driver.FindElement(By.Id("ctl00_ContentPlaceholder1_RadUpload1file0"));
String filePath = @"C:\MyProject\TestData.csv";
element.SendKeys(filePath);

-- File Upload Using FirefoxProfile
FirefoxProfile Prof = new FirefoxProfile();
Prof.setPreference("browser.download.dir", "D:\\java prj");
Prof.setPreference("browser.download.folderList", 2);
Prof.setPreference("browser.helperApps.neverAsk.saveToDisk","application/zip");
  
WebDriver driver = new FirefoxDriver(Prof);
driver.get("http://seleniumhq.org/download/");
driver.manage().timeouts().implicitlyWait(3,TimeUnit.MINUTES);
driver.findElement(By.xpath("//a[@name='client-drivers']/table/tbody/tr[1]/td[4]/a")).click();

```


## Scroll Up, Down Or Anywhere On A Page
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


```


## Setting proxy in Firefox

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



## Assert a Button Enabled or Disabled
```java


Check If an Element Is Visible
Assert.IsTrue(driver.FindElement(By.XPath("//*[@id='tve_editor']/div[2]/div[2]/div/div")).Displayed);

IWebElement button = driver.FindElement(By.XPath("/html/body/button"));
Assert.IsFalse(button.Enabled);
```



## License


## Links		
* [Automate Telerik Kendo Grid Webdriver](http://automatetheplanet.com/automate-telerik-kendo-grid-webdriver/)
* [Selenium Documentation](http://docs.seleniumhq.org/docs/)
* [Selenium API](https://selenium.googlecode.com/git/docs/api/java/overview-summary.html)
* [Test Activities](https://rtomac.github.io/robotframework-selenium2library/doc/Selenium2Library.html)
* [Basic of CSS Selector](https://robots.thoughtbot.com/basic-css-selectors-explained-with-cats)


## Example Links

### All Selenium Example

* [All Selenium Example](http://www.programcreek.com/java-api-examples/index.php?ClassName=selenium&submit=Search)

* [org.openqa.selenium.firefox.FirefoxDriver](http://www.programcreek.com/java-api-examples/index.php?api=org.openqa.selenium.firefox.FirefoxDriver)
* [org.openqa.selenium.chrome](http://www.programcreek.com/java-api-examples/index.php?api=org.openqa.selenium.chrome)
* [org.openqa.selenium.WebDriver](http://www.programcreek.com/java-api-examples/index.php?api=org.openqa.selenium.WebDriver)
* [org.openqa.selenium.WebElement](http://www.programcreek.com/java-api-examples/index.php?api=org.openqa.selenium.WebElement)
* [org.openqa.selenium.By](http://www.programcreek.com/java-api-examples/index.php?api=org.openqa.selenium.By)
* [org.openqa.selenium.support.ui.WebDriverWait](http://www.programcreek.com/java-api-examples/index.php?api=org.openqa.selenium.support.ui.WebDriverWait)
* [org.openqa.selenium.support.ui.FluentWait](http://www.programcreek.com/java-api-examples/index.php?api=org.openqa.selenium.support.ui.FluentWait)
* [org.openqa.selenium.support.ui.ExpectedCondition](http://www.programcreek.com/java-api-examples/index.php?api=org.openqa.selenium.support.ui.ExpectedCondition)
* [org.openqa.selenium.NoSuchElementException](http://www.programcreek.com/java-api-examples/index.php?api=org.openqa.selenium.NoSuchElementException)
* [org.openqa.selenium.StaleElementReferenceException](http://www.programcreek.com/java-api-examples/index.php?api=org.openqa.selenium.StaleElementReferenceException)
* [org.openqa.selenium.TimeoutException](http://www.programcreek.com/java-api-examples/index.php?api=org.openqa.selenium.TimeoutException)
* [org.openqa.selenium.interactions.Action](http://www.programcreek.com/java-api-examples/index.php?api=org.openqa.selenium.interactions.Action)
* [org.openqa.selenium.interactions.Actions](http://www.programcreek.com/java-api-examples/index.php?api=org.openqa.selenium.interactions.Actions)
* [org.openqa.selenium.Keys](http://www.programcreek.com/java-api-examples/index.php?api=org.openqa.selenium.Keys)
* [org.testng.annotations.Test](http://www.programcreek.com/java-api-examples/index.php?api=org.testng.annotations.Test)





