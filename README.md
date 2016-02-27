# SeleniumCheatSheet


## SeleniumCheatSheet
***

I am **bold**


```java
WebDriver driver = new FirefoxDriver();           //Firefox Driver
WebDriver driver = new ChromeDriver();            //Chrome Driver
WebDriver driver = new SafariDriver();            //Safari Driver
WebDriver driver = new InternetExplorerDriver();  //Internet Explorer Driver
WebDriver driver = new AndroidDriver()            //Android Driver
WebDriver driver = new IPhoneDriver();            //iPhone Driver
WebDriver driver = new HtmlUnitDriver()           //HTML Unit
```

## Chrome Driver
```java
System.setProperty("webdriver.chrome.driver", "/path/to/chromedriver");
WebDriver driver = new ChromeDriver();
```






```java
JavascriptExecutor js = (JavascriptExecutor) driver;
String js = "document.getElementsByName('fillname')[0].value='Selvi'";
js.executeScript(js);
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

```

Upload A File 
```java

```


##Scroll Up, Down Or Anywhere On A Page
JavascriptExecutor jsx = (JavascriptExecutor) driver;
//Vertical scroll - down by 100 pixels
jsx.executeScript("window.scrollBy(0,100)", "");
//Vertical scroll - up by 55 pixels (note the number is minus 55)
jsx.executeScript("window.scrollBy(0,-55)", "");
//Horizontal scroll - right by 20 pixels
jsx.executeScript("window.scrollBy(20,0)", "");
//Horizontal scroll - left by 95 pixels (note the number is minus 95)
jsx.executeScript("window.scrollBy(-95,0)", "");





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

FirefoxProfile Prof = new FirefoxProfile();
Prof.setPreference("browser.download.dir", "D:\\java prj");
Prof.setPreference("browser.download.folderList", 2);
Prof.setPreference("browser.helperApps.neverAsk.saveToDisk","application/zip");
  
WebDriver driver = new FirefoxDriver(Prof);
driver.get("http://seleniumhq.org/download/");
driver.manage().timeouts().implicitlyWait(3,TimeUnit.MINUTES);
driver.findElement(By.xpath("//a[@name='client-drivers']/table/tbody/tr[1]/td[4]/a")).click();


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
		
This is [an example](http://example.com/ "Optional Title") inline link.




