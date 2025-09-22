### Hybrid Automation Framework

This project is a hybrid automation framework built using Java, TestNG, and Maven, designed to support both UI and API test automation.

---

### Key Features
* **Hybrid Framework:** Supports both web UI automation using Selenium WebDriver and REST API testing using REST Assured.
* **Page Object Model (POM):** Follows the POM design pattern for maintainable and scalable UI tests.
* **Data-Driven Testing:** Utilizes TestNG's `@DataProvider` to run tests with multiple sets of data.
* **Parallel Execution:** Configured to run tests in parallel to reduce execution time.
* **Extensive Reporting:** Integrates with ExtentReports to generate detailed, visual test reports with screenshots on failure.
* **Centralized Configuration:** Manages application and API URLs, along with user credentials, in a central `application.properties` file.
* **CI/CD Integration:** Includes a `Jenkinsfile` for continuous integration with Jenkins.

---

### Prerequisites

* Java Development Kit (JDK) 8 or higher
* Maven 3.6.0 or higher

---

### Getting Started

1.  **Clone the repository:**
    ```bash
    git clone [repository-url]
    ```

2.  **Navigate to the project directory:**
    ```bash
    cd Hybrid-Automation-framework
    ```

3.  **Install dependencies and compile the project:**
    ```bash
    mvn clean install -DskipTests
    ```
    This command downloads all necessary dependencies and builds the project without running the tests.

---

### Project Structure
````

Hybrid-Automation-framework
├── src
│   ├── main
│   │   ├── java                    \# Main application code (POM classes, utilities, exceptions)
│   │   │   ├── io.learn.pages      \# Page Object Model classes
│   │   │   ├── io.learn.utils      \# Utility classes (WebDriver, ConfigReader)
│   │   │   └── io.learn.exceptions \# Custom exception classes
│   │   └── resources               \# Configuration files (log4j2.xml)
│   └── test
│       ├── java                    \# Test classes
│       │   ├── io.learn.api        \# API client classes
│       │   ├── io.learn.dataprovider \# Data providers
│       │   ├── io.learn.listener   \# TestNG listeners
│       │   └── io.learn.tests      \# Test classes (UI and API)
│       └── resources               \# Test resources (application.properties)
├── testng-api.xml                  \# TestNG suite for API tests
├── testng-datadriven.xml           \# TestNG suite for data-driven tests
├── testng-parallel.xml             \# TestNG suite for parallel test execution
├── testng-smoke-suite.xml          \# TestNG suite for smoke tests
├── testng.xml                      \# Default TestNG suite for UI regression tests
├── pom.xml                         \# Maven Project Object Model file
└── Jenkinsfile                     \# Jenkins pipeline script

````

---

### Test Execution

You can run tests using Maven and specifying a TestNG suite XML file.

* **Run all UI Regression Tests:**
    ```bash
    mvn clean test -DsuiteXMLFile=testng.xml
    ```

* **Run a specific suite (e.g., Smoke Tests):**
    ```bash
    mvn clean test -DsuiteXMLFile=testng-smoke-suite.xml
    ```

* **Run API Tests:**
    ```bash
    mvn clean test -DsuiteXMLFile=testng-api.xml
    ```
* **Run Data-Driven Tests:**
    ```bash
    mvn clean test -DsuiteXMLFile=testng-datadriven.xml
    ```

* **Run Tests in Parallel:**
    ```bash
    mvn clean test -DsuiteXMLFile=testng-parallel.xml
    ```

### Reporting

After test execution, reports will be generated in the `target/` directory:

* **UI Test Report:** `target/extent-reports.html`
* **API Test Report:** `target/extent-reports-api.html`
* **Test Logs:** `target/logs/test.log`
````
