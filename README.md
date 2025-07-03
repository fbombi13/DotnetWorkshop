# Test Automation Setup Using .NET and C#

This guide provides a step-by-step walkthrough for setting up a test automation project using .NET and C#. Follow each command to configure and initialize your environment.

---

## Step 1: List Available Templates

```bash
dotnet new --list
```

## Step 2: Create an NUnit Test Project

```bash
dotnet new nunit -n DotnetWorkshop
```

Before running the following commands be sure you are in the project folder

## Step 3: Running project
```bash
dotnet test
```

## Step 4: Add Selenium Packages
```bash
dotnet add package Selenium.WebDriver
```

```bash
dotnet add package WebDriverManager
```

## Step 5: Getting into UI Automation

Copy this:

```csharp
    private static readonly string _BASE_URL = "https://epam.com/";
    private readonly By _careersLink = By.LinkText("Careers");
    private readonly By _searchFormWrapper = By.Id("jobSearchFilterForm");
    private readonly By _searchFormKeyword = By.Id("new_form_job_search-keyword");
    private readonly By _searchFormLocation = By.ClassName("recruiting-search__location");
    private readonly By _searchFormLocationAllLocations = By.CssSelector("li[title='All Locations']");
    private readonly By _searchFormLocationLabel = By.XPath("//label[@for='new_form_job_search-location']");
    private readonly By _searchFormRemoteCheckbox = By.XPath("//label[normalize-space()='Remote']");
    private readonly By _searchFormFindButton = By.XPath("//form[@id='jobSearchFilterForm'] //button[normalize-space()='Find']");
    private readonly By _lastSearchResult = By.CssSelector(".search-result__item:last-of-type");
    private readonly By _resultHeadTitle = By.CssSelector(".heading-5");
    private readonly By _resultViewApplyButton = By.CssSelector(".search-result__item-controls a");
    private readonly By _vacancyJobTitle = By.ClassName("vacancy-details-23__job-title");
    private readonly By _magnifierIcon = By.CssSelector(".header-search__button");
    private readonly By _seachInput = By.CssSelector(".search-results__input-holder [name='q']");
    private readonly By _findButton = By.CssSelector(".search-results__action-section .custom-search-button");
    private readonly By _articlesFound = By.TagName("article");
    private readonly By _preloader = By.ClassName("preloader");

```

## Step 6: Use Driver Manager and Setup Hook

#### _Hint: Instantiate DriverManager_

## Step 7: Create Folder Structure

- Create Pages folder
- Create Tests
    - Move current test file into that folder, also rename if you want 

## Step 8: Add Actions into POM

## Step 9: Add configuration file for testing
Create an `appsettings.json` file


## Step 10: Add JSON Handler package

```bash
dotnet add package Microsoft.Extensions.Configuration.Json
```

## Step 11: Complete 'appsettings.json'
```JSON
{
  "TestSettings": {
    "BaseUrl": "https://example.com",
    "Browser": "Chrome",
    "Timeout": 30
  }
}
```

## Step 12: Run tests
```bash
dotnet test
```

## Step 13: Copy 'appsettings' on compiled area
```xml
<ItemGroup>
  <None Update="appsettings.json">
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </None>
</ItemGroup>
```

## Step 14: Configure IConfiguration
```csharp
 var builder = new ConfigurationBuilder()
    .SetBasePath(TestContext.CurrentContext.TestDirectory) // Set the base path
```
