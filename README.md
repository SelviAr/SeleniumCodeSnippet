# SeleniumCheatSheet


## SeleniumCheatSheet
***

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

## Android Driver
```java
WebDriver driver = new AndroidDriver()            
```

## Safari Driver
```java
WebDriver driver = new SafariDriver();            
```

## iPhone Driver
```java
WebDriver driver = new IPhoneDriver();            
```

## HTML Unit
```java
WebDriver driver = new HtmlUnitDriver()           
```

## RemoteWebDriver - Selenium Grid
```java
DesiredCapabilities safari = IOSCapabilities.iphone("Safari");
RemoteWebDriver driver = new RemoteWebDriver(new URL("http://localhost:5555/wd/hub"), safari);
```









## Navigation

```java

driver.navigate().refresh();

//Go back to the last visited page
driver.navigate().back();

//go forward to the next page
driver.navigate().forward();


```

## Waiting

```java
WebDriverWait wait = new WebDriverWait(driver, 30);
WebElement element = wait.until(ExpectedConditions.elementToBeClickable(By.id("id123")));
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
```

Upload A File 
```java

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

##Alert Screen

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


		
This is [an example](http://example.com/ "Optional Title") inline link.




