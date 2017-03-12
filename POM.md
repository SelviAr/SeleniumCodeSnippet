#Page Object Model (POM)




## PageObjects
``` java
class HomePage {

    WebDriver driver;

    public HomePage(driver) {
        this.driver = driver;
    }

    // Find a single element
    @FindBy(id="home-menu-entry")
    WebElement homeMenuEntry;

    public void clickHomeMenuEntry() {
        homeMenuEntry.click();
    }

    // Find several elements
    @FindBy(className="menu-entry")
    List<WebElement> menuEntries;

   // More actions and elements
}
``` 

## Usage of PageFactory and PageObject
class TestSomething {

    public void testMethod() {

        // Initial driver.

        // Use PageFactory to init elements.
        HomePage hp = PageFactory.initElements(driver, HomePage.class);

        // Use PageObject to execute action.
        hp.clickHomeMenuEntry();

        // Assertions or more actions.

    }

}





![1](https://solutionscafe.files.wordpress.com/2014/01/pom.jpg?w=300&h=66)
![1](http://cdn.guru99.com/images/AdvanceSelenium/071514_0722_PageObjectM1.png)
![1](http://cdn.guru99.com/images/AdvanceSelenium/071514_0722_PageObjectM2.png)
![1](http://cdn.guru99.com/images/AdvanceSelenium/071514_0722_PageObjectM3.png)
![1](http://cdn.guru99.com/images/AdvanceSelenium/071514_0722_PageObjectM4.png)
![1](https://solutionscafe.files.wordpress.com/2014/01/untitled14.png)
![1](https://solutionscafe.files.wordpress.com/2014/01/untitled15.png)
![1](https://solutionscafe.files.wordpress.com/2014/01/untitled.png)
![1](https://solutionscafe.files.wordpress.com/2014/01/untitled1.png)
![1](https://solutionscafe.files.wordpress.com/2014/01/untitled18.png)
![1](https://solutionscafe.files.wordpress.com/2014/01/untitled17.png)
![1](https://qxf2.com/blog/wp-content/uploads/2015/06/Gmail_POM-1.jpg)
