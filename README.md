# Repo3
1. Create Console application FlightSearchFunction in. Net using C# language.
2. Add a class named FlightSearchFunction.cs in project.
3. Go to Solution Explorer -->
	i) Project-->Reference-->Nuget Package Manager-->Search Nunit Framework--> Install
	ii) Project-->Reference-->Nuget Package Manager-->Search Selenium Webdriver--> Install
	iii) Project-->Reference-->Nuget Package Manager-->Search NunitTestAdapter--> Install

4. Write code in FlightSearchFunction.cs class

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using NUnit.Framework;
using OpenQA.Selenium.Firefox;
using OpenQA.Selenium.IE;
using OpenQA.Selenium;
using OpenQA.Selenium.Support.UI;

namespace FlightSearchFunction
{

    class FlightSearchFunction
    {
        IWebDriver driver;

        [SetUp]
        public void StartBrowser()
        {
            driver = new FirefoxDriver("C:\\");
            
        }
        [Test]
        public void StartTest()
        {
            driver.Url = "http://jt-dev.azurewebsites.net/#/SignUp";
            IWebElement webElement = driver.FindElement(By.XPath("//input[@id='name']"));
            webElement.SendKeys("Vinit");
            IWebElement webElementorg = driver.FindElement(By.XPath("//input[@id='orgName']"));
            webElementorg.SendKeys("Vinit");
            IWebElement webElementsignup = driver.FindElement(By.XPath("//input[@id='singUpEmail']"));
            webElementsignup.SendKeys("vinit.upadhyay1987@gmail.com");
            IWebElement webElementagree = driver.FindElement(By.XPath("//span[@class='black-color ng-binding']"));
            webElementagree.Click();
            IWebElement webElementgetstarted = driver.FindElement(By.XPath("//button[@class='btn btn-custom btn-block ng-binding']"));
            webElementgetstarted.Click();
        
        }

        [TearDown]
        public void CloseBrowser()
        {
          driver.Close();
        }
    }
}

5. Go to Test-->Windows--> Test Explorer
6. Run the test.
