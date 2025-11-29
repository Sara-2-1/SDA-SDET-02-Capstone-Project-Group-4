# Bazaar Stores Test Automation Framework

## Framework Overview
This is a **Selenium + Cucumber + Java + Maven** test automation framework with:

- Fluent Page Object Model design pattern
- BasePage with reusable methods
- AllPages class for centralized page object management
- Parallel execution support
- Multiple browser support (Chrome, Firefox, Edge)
- REST Assured integration for API testing
- ConfigReader for configuration management
- Cucumber BDD for readable test scenarios

---

## Project Structure
test-automation/
├── src/
│ ├── main/java/
│ └── test/
│ ├── java/
│ │ └── com/bazaarstores/
│ │ ├── pages/
│ │ ├── stepDefinitions/
│ │ ├── runners/
│ │ └── utilities/
│ └── resources/
│ └── features/
├── target/
│ ├── cucumber-reports/
│ └── screenshots/
├── pom.xml
└── configuration.properties

---

## Getting Started

### Prerequisites
- Java 21 or higher
- Maven 3.6+
- IDE (IntelliJ IDEA)

### Setup
1. Clone or download the framework
2. Import as Maven project
3. Update `configuration.properties` if needed
4. Run `mvn clean install` to download dependencies

---

## Maven Commands

### Execute All Tests
```bash
mvn clean test
# Smoke Tests
mvn clean test -Dtest=SmokeTestRunner

# API Tests
mvn clean test -Dtest=ApiTestRunner

# Regression Tests
mvn clean test -Dtest=TestRunner
# Chrome (default)
mvn clean test -Dbrowser=chrome

# Firefox
mvn clean test -Dbrowser=firefox

# Edge
mvn clean test -Dbrowser=edge

# Headless Chrome
mvn clean test -Dbrowser=chrome -Dheadless=true
# Run Smoke tests
mvn clean test -Dcucumber.filter.tags="@Smoke"

# Run Customer tests
mvn clean test -Dcucumber.filter.tags="@Customer"

# Run multiple tags
mvn clean test -Dcucumber.filter.tags="@Smoke and @Customer"

# Exclude tags
mvn clean test -Dcucumber.filter.tags="@Regression and not @API"
# Execute with 3 threads
mvn clean test -DthreadCount=3

# Execute with 5 threads
mvn clean test -DthreadCount=5
AllPages allPages = new AllPages(driver);
allPages.getLoginPage().enterEmail("test@test.com");
allPages.getDashboardPage().isDashboardPageDisplayed();
allPages.getLoginPage()
    .enterEmail("customer@sda.com")
    .enterPassword("Password.12345")
    .clickLoginButton();
String token = ApiUtil.loginAndGetToken(email, password);
base.url=https://bazaarstores.com
customer.email=customer@sda.com
admin.email=admin@sda.com
default.password=Password.12345
Writing New Tests
Create Feature File
Create Step Definitions
Create Page Object (if needed)
Add to AllPages class
Test Reports
HTML Report: target/cucumber-reports/cucumber.html
JSON Report: target/cucumber-reports/cucumber.json
XML Report: target/cucumber-reports/cucumber.xml
Screenshots: target/screenshots/ (on failure)
Configuration
Browser Configuration
browser=chrome
headless=false
Timeout Configuration
implicit.wait=10
explicit.wait=15
page.load.timeout=30
User Roles
customer.email=customer@sda.com
admin.email=admin@sda.com
storemanager.email=storemanager@sda.com
default.password=Password.12345
Contributing
Add feature file in src/test/resources/features/
Create step definitions in stepDefinitions/
Create page objects in pages/ extending BasePage
Add page getter to AllPages class
Update configuration if needed
Support & Resources
Application URL: https://bazaarstores.com/
Swagger API: https://bazaarstores.com/api/documentation
Framework: Selenium 4.15.0 + Cucumber 7.14.0
Build Tool: Maven
Language: Java 21
