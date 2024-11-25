# fitpeo

# FitPeoAutomation - Selenium Java Script

This project demonstrates a basic Selenium automation script written in Java. The script performs various actions on the [FitPeo website](https://www.fitpeo.com/) such as interacting with sliders, input fields, checkboxes, and verifying web page elements.

## Prerequisites

1. **Java Development Kit (JDK):** Ensure you have JDK 8 or higher installed.
2. **Selenium WebDriver:** Download the Selenium Java library and add it to your project.
3. **ChromeDriver:** Download the version compatible with your Google Chrome browser and provide the correct path in the script.
4. **IDE:** Use an Integrated Development Environment (IDE) like IntelliJ IDEA or Eclipse for writing and running the code.

## Features

- Opens the FitPeo website.
- Clicks the "Revenue Calculator" button.
- Adjusts a slider to a specific value.
- Inputs a value into a text box and verifies the slider reflects the input.
- Selects checkboxes based on specified conditions.
- Verifies the presence and correctness of a header displaying reimbursement information.

## Setup

1. Clone or download the repository.
2. Update the `path/to/chromedriver` in the script with the actual path to your ChromeDriver executable.
3. Ensure all required dependencies (e.g., Selenium JAR files) are added to your project classpath.

## Execution Steps

1. Compile the Java file:
   ```bash
   javac FitPeoAutomation.java
   ```
2. Run the script:
   ```bash
   java FitPeoAutomation
   ```

## Code Highlights

1. **Navigate to FitPeo:**
   ```java
   driver.get("https://www.fitpeo.com/");
   ```
2. **Interact with sliders and text boxes:**
   ```java
   WebElement slider = driver.findElement(By.xpath("//input[@type='range']"));
   String script = "arguments[0].value = 820;";
   ((org.openqa.selenium.JavascriptExecutor) driver).executeScript(script, slider);
   ```
3. **Select checkboxes dynamically:**
   ```java
   WebElement checkbox57 = driver.findElement(By.xpath("//span[contains(text(),'57')]/preceding-sibling::span"));
   if (!checkbox57.isSelected()) {
       checkbox57.click();
   }
   ```
4. **Verify header content:**
   ```java
   WebElement totalReimbursementHeader = driver.findElement(By.xpath("//header[contains(text(),'Total Recurring Reimbursement for all Patients Per Month:')]");
   System.out.println("Header verification: " + (headerText.contains("$75600") ? "Passed" : "Failed") + ". Header text: " + headerText);
   ```

## Expected Output

- The script prints:
  - The page title.
  - Confirmation of slider and text box synchronization.
  - Checkbox selections.
  - Verification results of the reimbursement header.

## Notes

- Ensure the website's structure (like XPath values) matches the script. Update XPaths if the website changes.
- Handle exceptions for smoother execution and better debugging.

## Contributing

Feel free to contribute by submitting pull requests or suggesting improvements.

## License

This project is open-source. Modify and use it as per your needs.

