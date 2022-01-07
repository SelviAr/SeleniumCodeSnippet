# Instantiate WebDriver using Firefox Driver:

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
System.setProperty("webdriver.gecko.driver", "<Gecko Driver executable location on your system>"); 
WebDriver driver = new FirefoxDriver();

# Instantiate WebDriver using Chrome Driver:

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
System.setProperty("webdriver.chrome.driver", "Chrome Driver executable location on your system"); 
WebDriver driver = new ChromeDriver();


# How to navigate to a web page using Selenium WebDriver?
driver.get("https://demoqa.com/login");


# Maximize browser window using Selenium Webdriver?
driver.manage().window().maximize();


# Retrieve the title of the page:
String title = driver.getTitle();
System.out.println("The page title is : " +title);


# How to locate a web element on a web page using Selenium WebDriver?
import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;

WebElement uName = driver.findElement(By.xpath("//*[@id='userName']"));
WebElement pswd = driver.findElement(By.xpath("//*[@id='password']"));
WebElement loginBtn = driver.findElement(By.xpath("//*[@id='login']"))


# How to perform actions on web elements using Selenium WebDriver?

uName.sendKeys("testuser");
pswd.sendKeys("Password@123");
loginBtn.click();
loginBtn.submit();
txtname.clear()


# How to perform validations on web elements using Selenium WebDriver?
try {
			
WebElement logoutBtn = driver.findElement(By.xpath("//div[@class='text-right col-md-5 col-sm-12']//button[@id='submit']"));
							
if(logoutBtn.isDisplayed()){
   logoutBtn.click();
   System.out.println("LogOut Successful!");
 }
} 
catch (Exception e) {
     System.out.println("Incorrect login....");
}


# How to close the browser using Selenium WebDriver?
driver.quit();



# Full Code

package firstPackage;

import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class MyFirstTestClass {

	public static void main(String[] args){
		//Setting the driver path
		System.setProperty("webdriver.chrome.driver", "E:\\Softwares\\chromedriver.exe");
		
		//Creating WebDriver instance
		WebDriver driver = new ChromeDriver();
		
		//Navigate to web page
		driver.get("https://demoqa.com/login");
		
		//Maximizing window
		driver.manage().window().maximize();
		
		//Retrieving web page title
		String title = driver.getTitle();
		System.out.println("The page title is : " +title);
		
		//Locating web element
		WebElement uName = driver.findElement(By.xpath("//*[@id='userName']"));
		WebElement pswd = driver.findElement(By.xpath("//*[@id='password']"));
		WebElement loginBtn = driver.findElement(By.xpath("//*[@id='login']"));
		
		
		//Peforming actions on web elements
		uName.sendKeys("testuser");
		pswd.sendKeys("Password@123");
		loginBtn.click();
		
		//Putting implicit wait
		driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
		
		try {
			
			//Locating web element
			WebElement logoutBtn = driver.findElement(By.xpath("//div[@class='text-right col-md-5 col-sm-12']//button[@id='submit']"));
			//Validating presence of element				
			if(logoutBtn.isDisplayed()){
				
				//Performing action on web element
				logoutBtn.click();
				System.out.println("LogOut Successful!");
			}
		} 
		catch (Exception e) {
			System.out.println("Incorrect login....");
		}
		
		//Closing browser session
		driver.quit();
		
	}

}


# How to setup Selenium GeckoDriver by Setting up Desired capabilities for the browser?
System.out.println("Execution with desired capabilities");
DesiredCapabilities cap = DesiredCapabilities.firefox();
cap.setCapability("marionette", true);
WebDriver driver = new FirefoxDriver(cap);
driver.get("https://demoqa.com");
Thread.sleep(3000);
driver.quit();
System.out.println("Execution completed");


# How to run tests in Headless mode using GeckoDriver?


package gecko;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.firefox.FirefoxOptions;

public class GeckoDriver {

	public static void main(String[] args) throws InterruptedException {

		System.out.println("Execution in Headless Mode");
                FirefoxOptions options = new FirefoxOptions();  
	        options.setHeadless(true); 
		WebDriver driver = new FirefoxDriver(options);
		driver.get("https://demoqa.com");
		Thread.sleep(3000);
		System.out.println("The page title is " +driver.getTitle());
		driver.quit();
		System.out.println("Execution completed");
	}

}

