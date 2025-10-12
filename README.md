# note



# 🧪 Software Testing and Quality Assurance (STQA) Journal

This repository contains comprehensive practical implementations and exercises for Software Testing and Quality Assurance using Selenium IDE and Selenium WebDriver, covering automated testing techniques, data manipulation, and web element analysis.

---

## 📚 Table of Contents

1. [Practical 1: Selenium IDE Test Suite Creation](#practical-1-selenium-ide-test-suite-creation)
2. [Practical 2: Cross-Website Testing with Selenium IDE](#practical-2-cross-website-testing-with-selenium-ide)
3. [Practical 3: Login Automation with Selenium WebDriver](#practical-3-login-automation-with-selenium-webdriver)
4. [Practical 4: Excel Data Manipulation and Verification](#practical-4-excel-data-manipulation-and-verification)
5. [Practical 5: Excel Data Extraction and Analysis](#practical-5-excel-data-extraction-and-analysis)
6. [Practical 6: Web Page Object Counting](#practical-6-web-page-object-counting)
7. [Practical 7: Dropdown/Combo Box Analysis](#practical-7-dropdowncombo-box-analysis)
8. [Practical 8: Checkbox State Analysis](#practical-8-checkbox-state-analysis)

---

## Practical 1: Selenium IDE Test Suite Creation

### **AIM**
Install Selenium IDE and create a test suite containing a minimum of 4 test cases for different web page formats (e.g., HTML, XML, JSON, etc.).

### 🔧 **Tools Required**
- **Web Browser** (Chrome/Firefox)
- **Selenium IDE Extension**
- **NetBeans IDE**
- **Apache Tomcat Server**

### 🚀 **Procedure**

#### 1. Selenium IDE Installation:
1. **Install Selenium IDE Extension**
   - Open your browser (Chrome/Firefox)
   - Search for "Selenium IDE"
   - Click on the first link from official Selenium website
   - Add the "Selenium IDE" extension to your browser

#### 2. Web Application Setup:
2. **Create Test Web Application**
   - Open **NetBeans IDE**
   - Go to **File** → **New Project**
   - Select **Java Web** → **Web Application**
   - Add **Apache Tomcat server**
   - Click **Finish**

#### 3. Test Case Implementation:

3. **Create Arithmetic Operations Test Suite**

**index.html:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>STQA Practical 1 - Arithmetic Operations</title>
    <script language="javascript">
        function addition() {
            var num1 = parseInt(document.arithmetic.n1.value);
            var num2 = parseInt(document.arithmetic.n2.value);
            var result = num1 + num2;
            document.arithmetic.result.value = result;
        }
        
        function subtraction() {
            var num1 = parseInt(document.arithmetic.n1.value);
            var num2 = parseInt(document.arithmetic.n2.value);
            var result = num1 - num2;
            document.arithmetic.result.value = result;
        }
        
        function multiplication() {
            var num1 = parseInt(document.arithmetic.n1.value);
            var num2 = parseInt(document.arithmetic.n2.value);
            var result = num1 * num2;
            document.arithmetic.result.value = result;
        }
        
        function division() {
            var num1 = parseInt(document.arithmetic.n1.value);
            var num2 = parseInt(document.arithmetic.n2.value);
            if (num2 !== 0) {
                var result = num1 / num2;
                document.arithmetic.result.value = result;
            } else {
                document.arithmetic.result.value = "Error: Division by zero";
            }
        }
    </script>
</head>
<body>
    <h2>Arithmetic Operations Test Suite</h2>
    
    <form name="arithmetic">
        <table border="1" cellpadding="5">
            <tr>
                <td>First Number:</td>
                <td><input type="text" name="n1" id="num1"></td>
            </tr>
            <tr>
                <td>Second Number:</td>
                <td><input type="text" name="n2" id="num2"></td>
            </tr>
            <tr>
                <td>Result:</td>
                <td><input type="text" name="result" id="result" readonly></td>
            </tr>
            <tr>
                <td colspan="2" align="center">
                    <input type="button" value="Add" onclick="addition()" id="addBtn">
                    <input type="button" value="Subtract" onclick="subtraction()" id="subBtn">
                    <input type="button" value="Multiply" onclick="multiplication()" id="mulBtn">
                    <input type="button" value="Divide" onclick="division()" id="divBtn">
                </td>
            </tr>
        </table>
    </form>
</body>
</html>
```

**newjsp.jsp:**
```jsp
<%@ page contentType="text/html" pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title>STQA Test Navigation</title>
</head>
<body>
    <h1>Welcome to STQA Testing Suite</h1>
    <a href="index.html">Go to Arithmetic Operations Test</a>
</body>
</html>
```

#### 4. Selenium IDE Test Recording:

4. **Record Test Cases**
   - Run the JSP file in browser to access the arithmetic operations page
   - Copy the page URL from browser address bar
   - Open **Selenium IDE** extension
   - Click **"Create a new project"**
   - Enter project name: "ArithmeticOperationsTest"
   - Click **"Start Recording"**
   
5. **Perform Test Actions**
   - Enter test values in input fields
   - Click each operation button (Add, Subtract, Multiply, Divide)
   - Verify results for each operation
   - Stop recording when done

6. **Save and Execute Tests**
   - Name each test case:
     - Test Case 1: "AdditionTest"
     - Test Case 2: "SubtractionTest"  
     - Test Case 3: "MultiplicationTest"
     - Test Case 4: "DivisionTest"
   - Click **"Run all tests"** to execute the complete test suite
   - Review test results and logs

### 📊 **Expected Test Scenarios**
- **Addition Test:** 5 + 3 = 8
- **Subtraction Test:** 10 - 4 = 6
- **Multiplication Test:** 6 × 7 = 42
- **Division Test:** 15 ÷ 3 = 5

---

## Practical 2: Cross-Website Testing with Selenium IDE

### **AIM**
Conduct a test suite for two different websites using Selenium IDE. Perform various actions like clicking links, filling forms, and verifying content.

### 🔧 **Tools Required**
- **Selenium IDE** (Browser Extension)
- **Target Website:** redbus.in (or similar)

### 🚀 **Procedure**

#### 1. Setup and Recording:
1. **Initialize Selenium IDE**
   - Ensure Selenium IDE extension is installed
   - Open target website (e.g., redbus.in)
   - Copy the website URL

2. **Start New Test Project**
   - Open Selenium IDE
   - Create new project: "WebsiteTestSuite"
   - Paste the copied URL as base URL
   - Click **"Start Recording"**

#### 2. Test Commands and Actions:

3. **Essential Selenium IDE Commands**

   **Verification Commands:**
   ```javascript
   // Verify page title
   verifyTitle | RedBus Online Bus Ticket Booking
   
   // Assert specific text exists
   assertText | css=.main-header | Welcome to RedBus
   
   // Store text value in variable
   storeText | css=.price-display | ticketPrice
   
   // Output stored variable to log
   echo | ${ticketPrice}
   ```

4. **Interactive Test Sequence**
   - **Search for buses:** Enter source and destination cities
   - **Select travel date:** Use date picker
   - **Click search button:** Initiate bus search
   - **Assert bus results:** Verify bus provider names appear
   - **Store ticket prices:** Capture pricing information
   - **Echo stored values:** Display captured data in log

#### 3. Advanced Test Actions:

5. **Form Interaction Tests**
   ```javascript
   // Click on element
   click | id=source-city-input
   
   // Type text in input field
   type | id=source-city-input | Mumbai
   
   // Select from dropdown
   select | name=travel-class | value=AC
   
   // Wait for element to be present
   waitForElementPresent | css=.search-results | 5000
   ```

6. **Content Verification Tests**
   ```javascript
   // Verify element is visible  
   verifyElementPresent | css=.bus-item
   
   // Assert text contains specific content
   assertTextPresent | Available buses
   
   // Verify link is clickable
   verifyElementClickable | css=.book-now-btn
   ```

#### 4. Execution and Analysis:

7. **Run Test Suite**
   - Stop recording after completing all interactions
   - Name test cases appropriately:
     - "BusSearchTest"
     - "PriceVerificationTest"
     - "BookingFormTest"
   - Execute complete test suite
   - Analyze results in test log

### 📋 **Test Case Examples**

#### Test Case 1: Basic Navigation
```javascript
open | https://www.redbus.in
verifyTitle | RedBus: Book Bus Tickets Online
click | link=Help
verifyTextPresent | Customer Support
```

#### Test Case 2: Search Functionality
```javascript
type | id=src | Mumbai
type | id=dest | Pune  
click | id=search-button
waitForElementPresent | css=.bus-results
assertElementPresent | css=.bus-item
```

---

## Practical 3: Login Automation with Selenium WebDriver

### **AIM**
Write a program using Selenium WebDriver to automate the login process on a specific web page. Verify successful login with appropriate assertions.

### 🔧 **Tools Required**
- **Selenium WebDriver**
- **Java Development Environment**
- **Firefox Browser**
- **GeckoDriver**

### 🚀 **Procedure**

#### 1. Environment Setup:

1. **Java Project Configuration**
   - Create new Java project in IDE
   - Add Selenium WebDriver JAR files to build path
   - Download and configure GeckoDriver for Firefox

#### 2. WebDriver Implementation:

2. **Basic WebDriver Setup**

```java
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.remote.DesiredCapabilities;

public class LoginAutomation {
    
    public static void main(String[] args) {
        
        // Set GeckoDriver path
        String driverPath = "path/to/geckodriver.exe";
        System.setProperty("webdriver.gecko.driver", driverPath);
        
        // Configure Firefox capabilities
        DesiredCapabilities capabilities = DesiredCapabilities.firefox();
        capabilities.setCapability("marionette", true);
        
        // Initialize WebDriver
        WebDriver driver = new FirefoxDriver(capabilities);
        
        try {
            // Navigate to target website
            driver.get("http://www.example-login-site.com");
            
            // Maximize browser window
            driver.manage().window().maximize();
            
            // Add login automation logic here
            performLogin(driver);
            
        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            // Close browser
            driver.quit();
        }
    }
    
    private static void performLogin(WebDriver driver) {
        // Login implementation will be added here
        System.out.println("Login automation executed successfully");
    }
}
```

#### 3. Enhanced Login Automation:

3. **Complete Login Implementation**

```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.support.ui.WebDriverWait;
import org.openqa.selenium.support.ui.ExpectedConditions;
import java.time.Duration;

public class CompleteLoginAutomation {
    
    private static WebDriver driver;
    private static WebDriverWait wait;
    
    public static void main(String[] args) {
        
        // Setup WebDriver
        setupDriver();
        
        try {
            // Navigate to login page
            driver.get("https://example-login-site.com/login");
            
            // Perform login
            boolean loginSuccess = performLogin("testuser@example.com", "password123");
            
            // Verify login success
            if (loginSuccess) {
                System.out.println("✅ Login successful!");
                verifySuccessfulLogin();
            } else {
                System.out.println("❌ Login failed!");
            }
            
        } catch (Exception e) {
            System.err.println("Error during automation: " + e.getMessage());
        } finally {
            // Cleanup
            driver.quit();
        }
    }
    
    private static void setupDriver() {
        System.setProperty("webdriver.gecko.driver", "path/to/geckodriver.exe");
        driver = new FirefoxDriver();
        wait = new WebDriverWait(driver, Duration.ofSeconds(10));
        driver.manage().window().maximize();
    }
    
    private static boolean performLogin(String username, String password) {
        try {
            // Wait for username field and enter credentials
            WebElement usernameField = wait.until(
                ExpectedConditions.presenceOfElementLocated(By.id("username"))
            );
            usernameField.clear();
            usernameField.sendKeys(username);
            
            // Enter password
            WebElement passwordField = driver.findElement(By.id("password"));
            passwordField.clear();
            passwordField.sendKeys(password);
            
            // Click login button
            WebElement loginButton = driver.findElement(By.id("login-btn"));
            loginButton.click();
            
            // Wait for page to load
            Thread.sleep(3000);
            
            return true;
            
        } catch (Exception e) {
            System.err.println("Login failed: " + e.getMessage());
            return false;
        }
    }
    
    private static void verifySuccessfulLogin() {
        try {
            // Check for success indicators
            WebElement welcomeMessage = wait.until(
                ExpectedConditions.presenceOfElementLocated(By.className("welcome-message"))
            );
            
            if (welcomeMessage.isDisplayed()) {
                System.out.println("✅ Login verification successful: " + welcomeMessage.getText());
            }
            
            // Verify URL change
            String currentUrl = driver.getCurrentUrl();
            if (currentUrl.contains("dashboard") || currentUrl.contains("home")) {
                System.out.println("✅ URL verification successful: " + currentUrl);
            }
            
            // Check for logout button presence
            WebElement logoutButton = driver.findElement(By.id("logout-btn"));
            if (logoutButton.isDisplayed()) {
                System.out.println("✅ Logout button verification successful");
            }
            
        } catch (Exception e) {
            System.err.println("Login verification failed: " + e.getMessage());
        }
    }
}
```

### 🔍 **Key Testing Points**
- **Element presence verification** before interaction
- **Proper wait mechanisms** for dynamic content
- **Multiple verification methods** for login success
- **Error handling** for failed login attempts
- **Clean browser session management**

---

## Practical 4: Excel Data Manipulation and Verification

### **AIM**
Write a program using Selenium WebDriver to update 10 student records in an Excel file. Perform data manipulation and verification.

### 🔧 **Tools Required**
- **Selenium WebDriver**
- **Java (Eclipse IDE)**
- **TestNG Framework**
- **JXL Library** (Java Excel API)

### 🚀 **Procedure**

#### 1. Project Setup:

1. **Eclipse Project Configuration**
   - Create new Java project in Eclipse IDE
   - Configure build path to include necessary JAR files:
     - Selenium WebDriver JARs
     - TestNG JAR
     - JXL (Java Excel) JAR

#### 2. Excel File Preparation:

2. **Create Input Excel File (Students.xls)**

| Roll No | Name        | Subject1 | Subject2 | Subject3 | Total | Result |
|---------|-------------|----------|----------|----------|-------|--------|
| 101     | John Doe    | 45       | 67       | 78       |       |        |
| 102     | Jane Smith  | 34       | 56       | 89       |       |        |
| 103     | Mike Johnson| 67       | 78       | 45       |       |        |
| 104     | Emily Davis | 23       | 45       | 67       |       |        |
| 105     | Chris Wilson| 78       | 89       | 90       |       |        |
| 106     | Sarah Brown | 56       | 67       | 78       |       |        |
| 107     | David Lee   | 89       | 90       | 91       |       |        |
| 108     | Lisa Garcia | 12       | 34       | 56       |       |        |
| 109     | Tom Miller  | 67       | 78       | 89       |       |        |
| 110     | Amy Taylor  | 45       | 67       | 89       |       |        |

3. **Create Output Excel File (results.xls)**
   - Initially empty file with same structure
   - Will be populated by the program

#### 3. Java Implementation:

4. **Complete Excel Processing Program**

```java
import java.io.File;
import java.io.IOException;
import jxl.*;
import jxl.read.biff.BiffException;
import jxl.write.*;
import jxl.write.Number;

public class ExcelDataProcessor {
    
    public static void main(String[] args) {
        
        try {
            // Read input Excel file
            Workbook inputWorkbook = Workbook.getWorkbook(new File("Students.xls"));
            Sheet inputSheet = inputWorkbook.getSheet(0);
            
            // Create output Excel file
            WritableWorkbook outputWorkbook = Workbook.createWorkbook(new File("results.xls"));
            WritableSheet outputSheet = outputWorkbook.createSheet("Student Results", 0);
            
            // Copy headers
            copyHeaders(inputSheet, outputSheet);
            
            // Process student data
            processStudentRecords(inputSheet, outputSheet);
            
            // Write and close files
            outputWorkbook.write();
            outputWorkbook.close();
            inputWorkbook.close();
            
            System.out.println("✅ Excel processing completed successfully!");
            System.out.println("📊 Results saved to results.xls");
            
        } catch (Exception e) {
            System.err.println("❌ Error processing Excel file: " + e.getMessage());
            e.printStackTrace();
        }
    }
    
    private static void copyHeaders(Sheet inputSheet, WritableSheet outputSheet) 
            throws WriteException {
        
        // Copy all headers from input to output
        for (int col = 0; col < inputSheet.getColumns(); col++) {
            Cell headerCell = inputSheet.getCell(col, 0);
            Label headerLabel = new Label(col, 0, headerCell.getContents());
            outputSheet.addCell(headerLabel);
        }
        
        // Add new headers for calculated fields
        Label totalHeader = new Label(5, 0, "Total");
        Label resultHeader = new Label(6, 0, "Result");
        outputSheet.addCell(totalHeader);
        outputSheet.addCell(resultHeader);
    }
    
    private static void processStudentRecords(Sheet inputSheet, WritableSheet outputSheet) 
            throws WriteException {
        
        int passCount = 0;
        int failCount = 0;
        
        // Process each student record (starting from row 1, skipping header)
        for (int row = 1; row < inputSheet.getRows(); row++) {
            
            // Copy basic student information
            for (int col = 0; col < 5; col++) {
                Cell cell = inputSheet.getCell(col, row);
                Label label = new Label(col, row, cell.getContents());
                outputSheet.addCell(label);
            }
            
            // Get subject scores
            int subject1 = Integer.parseInt(inputSheet.getCell(2, row).getContents());
            int subject2 = Integer.parseInt(inputSheet.getCell(3, row).getContents());
            int subject3 = Integer.parseInt(inputSheet.getCell(4, row).getContents());
            
            // Calculate total
            int total = subject1 + subject2 + subject3;
            Number totalCell = new Number(5, row, total);
            outputSheet.addCell(totalCell);
            
            // Determine result (Pass if all subjects > 35)
            String result;
            if (subject1 > 35 && subject2 > 35 && subject3 > 35) {
                result = "Pass";
                passCount++;
            } else {
                result = "Fail";  
                failCount++;
            }
            
            Label resultCell = new Label(6, row, result);
            outputSheet.addCell(resultCell);
            
            // Print processing status
            String studentName = inputSheet.getCell(1, row).getContents();
            System.out.println("Processed: " + studentName + " - Total: " + total + " - Result: " + result);
        }
        
        // Print summary statistics
        System.out.println("\n📈 PROCESSING SUMMARY:");
        System.out.println("✅ Students Passed: " + passCount);
        System.out.println("❌ Students Failed: " + failCount);
        System.out.println("📊 Total Students Processed: " + (passCount + failCount));
    }
}
```

#### 4. Enhanced Processing with TestNG:

5. **TestNG Integration**

```java
import org.testng.annotations.Test;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.AfterClass;
import org.testng.Assert;

public class ExcelProcessingTest {
    
    private String inputFile = "Students.xls";
    private String outputFile = "results.xls";
    
    @BeforeClass
    public void setUp() {
        System.out.println("🚀 Starting Excel processing test...");
        // Verify input file exists
        File input = new File(inputFile);
        Assert.assertTrue(input.exists(), "Input file must exist: " + inputFile);
    }
    
    @Test
    public void testExcelProcessing() {
        try {
            // Execute processing
            ExcelDataProcessor processor = new ExcelDataProcessor();
            processor.processExcelFile(inputFile, outputFile);
            
            // Verify output file was created
            File output = new File(outputFile);
            Assert.assertTrue(output.exists(), "Output file should be created");
            
            // Verify data integrity
            verifyProcessedData();
            
        } catch (Exception e) {
            Assert.fail("Excel processing failed: " + e.getMessage());
        }
    }
    
    private void verifyProcessedData() throws Exception {
        Workbook resultWorkbook = Workbook.getWorkbook(new File(outputFile));
        Sheet resultSheet = resultWorkbook.getSheet(0);
        
        // Verify headers
        Assert.assertEquals(resultSheet.getCell(6, 0).getContents(), "Result");
        
        // Verify sample calculations
        int sampleTotal = Integer.parseInt(resultSheet.getCell(5, 1).getContents());
        String sampleResult = resultSheet.getCell(6, 1).getContents();
        
        System.out.println("✅ Sample verification - Total: " + sampleTotal + ", Result: " + sampleResult);
        
        resultWorkbook.close();
    }
    
    @AfterClass  
    public void tearDown() {
        System.out.println("🏁 Excel processing test completed!");
    }
}
```

### 📊 **Expected Output**
- **results.xls** file with processed student data
- **Total scores** calculated for each student
- **Pass/Fail results** based on minimum score criteria (>35 in each subject)
- **Console summary** showing processing statistics

---

## Practical 5: Excel Data Extraction and Analysis

### **AIM**
Write a program using Selenium WebDriver to select the number of students who have scored more than 60 in any one subject (or all subjects). Perform data extraction and analysis.

### 🔧 **Tools Required**
- **Selenium WebDriver**
- **Java**
- **Eclipse IDE**
- **JXL Library**
- **TestNG Framework**

### 🚀 **Procedure**

#### 1. Project Setup:

1. **Environment Configuration**
   - Similar setup as Practical 4
   - Create input file: `Students.xls`
   - Create output file: `results1.xls`

#### 2. Enhanced Student Data Analysis:

2. **Advanced Excel Processing Program**

```java
import java.io.File;
import jxl.*;
import jxl.write.*;
import jxl.write.Number;

public class AdvancedExcelAnalyzer {
    
    public static void main(String[] args) {
        
        try {
            // Read input data
            Workbook inputWorkbook = Workbook.getWorkbook(new File("Students.xls"));
            Sheet inputSheet = inputWorkbook.getSheet(0);
            
            // Create output workbook
            WritableWorkbook outputWorkbook = Workbook.createWorkbook(new File("results1.xls"));
            WritableSheet outputSheet = outputWorkbook.createSheet("High Performers", 0);
            
            // Analyze and filter student data
            analyzeStudentPerformance(inputSheet, outputSheet);
            
            // Write results
            outputWorkbook.write();
            outputWorkbook.close();
            inputWorkbook.close();
            
            System.out.println("✅ Advanced analysis completed!");
            
        } catch (Exception e) {
            System.err.println("❌ Analysis failed: " + e.getMessage());
            e.printStackTrace();
        }
    }
    
    private static void analyzeStudentPerformance(Sheet inputSheet, WritableSheet outputSheet) 
            throws WriteException {
        
        // Create headers for filtered results
        String[] headers = {"Roll No", "Name", "Subject1", "Subject2", "Subject3", "Max Score", "Category"};
        for (int i = 0; i < headers.length; i++) {
            Label header = new Label(i, 0, headers[i]);
            outputSheet.addCell(header);
        }
        
        int outputRow = 1;
        int highPerformersCount = 0;
        int allSubjectsAbove60Count = 0;
        
        // Analyze each student
        for (int row = 1; row < inputSheet.getRows(); row++) {
            
            // Get student data
            String rollNo = inputSheet.getCell(0, row).getContents();
            String name = inputSheet.getCell(1, row).getContents();
            int subject1 = Integer.parseInt(inputSheet.getCell(2, row).getContents());
            int subject2 = Integer.parseInt(inputSheet.getCell(3, row).getContents());
            int subject3 = Integer.parseInt(inputSheet.getCell(4, row).getContents());
            
            // Check performance criteria
            boolean hasSubjectAbove60 = (subject1 > 60 || subject2 > 60 || subject3 > 60);
            boolean allSubjectsAbove60 = (subject1 > 60 && subject2 > 60 && subject3 > 60);
            
            // Filter based on criteria
            if (hasSubjectAbove60) {
                
                // Copy student data to output
                outputSheet.addCell(new Label(0, outputRow, rollNo));
                outputSheet.addCell(new Label(1, outputRow, name));
                outputSheet.addCell(new Number(2, outputRow, subject1));
                outputSheet.addCell(new Number(3, outputRow, subject2));
                outputSheet.addCell(new Number(4, outputRow, subject3));
                
                // Calculate maximum score
                int maxScore = Math.max(Math.max(subject1, subject2), subject3);
                outputSheet.addCell(new Number(5, outputRow, maxScore));
                
                // Categorize performance
                String category;
                if (allSubjectsAbove60) {
                    category = "All Subjects >60";
                    allSubjectsAbove60Count++;
                } else {
                    category = "At Least One >60";
                }
                
                outputSheet.addCell(new Label(6, outputRow, category));
                
                outputRow++;
                highPerformersCount++;
                
                // Print student details
                System.out.println("High Performer: " + name + " (Max: " + maxScore + ") - " + category);
            }
        }
        
        // Add summary section
        addSummarySection(outputSheet, outputRow + 2, highPerformersCount, allSubjectsAbove60Count);
    }
    
    private static void addSummarySection(WritableSheet sheet, int startRow, 
                                        int totalHighPerformers, int allAbove60) 
            throws WriteException {
        
        // Summary headers
        Label summaryHeader = new Label(0, startRow, "ANALYSIS SUMMARY");
        sheet.addCell(summaryHeader);
        
        // Summary data  
        sheet.addCell(new Label(0, startRow + 2, "Students with at least one subject >60:"));
        sheet.addCell(new Number(1, startRow + 2, totalHighPerformers));
        
        sheet.addCell(new Label(0, startRow + 3, "Students with all subjects >60:"));
        sheet.addCell(new Number(1, startRow + 3, allAbove60));
        
        sheet.addCell(new Label(0, startRow + 4, "Percentage of high performers:"));
        double percentage = (totalHighPerformers / 10.0) * 100; // Assuming 10 total students
        sheet.addCell(new Number(1, startRow + 4, percentage));
        
        // Print console summary
        System.out.println("\n📊 ANALYSIS SUMMARY:");
        System.out.println("🎯 Students with at least one subject >60: " + totalHighPerformers);
        System.out.println("🏆 Students with all subjects >60: " + allAbove60);
        System.out.println("📈 High performer percentage: " + percentage + "%");
    }
}
```

#### 3. Statistical Analysis Enhancement:

3. **Advanced Statistical Analysis**

```java
import java.util.*;

public class StudentStatisticsAnalyzer {
    
    public static void performStatisticalAnalysis(Sheet inputSheet) throws Exception {
        
        List<StudentRecord> students = new ArrayList<>();
        
        // Load all student data
        for (int row = 1; row < inputSheet.getRows(); row++) {
            StudentRecord student = new StudentRecord(
                inputSheet.getCell(0, row).getContents(), // Roll No
                inputSheet.getCell(1, row).getContents(), // Name
                Integer.parseInt(inputSheet.getCell(2, row).getContents()), // Subject1
                Integer.parseInt(inputSheet.getCell(3, row).getContents()), // Subject2
                Integer.parseInt(inputSheet.getCell(4, row).getContents())  // Subject3
            );
            students.add(student);
        }
        
        // Perform various analyses
        analyzeSubjectWisePerformance(students);
        findTopPerformers(students);
        calculateClassStatistics(students);
    }
    
    private static void analyzeSubjectWisePerformance(List<StudentRecord> students) {
        System.out.println("\n📚 SUBJECT-WISE ANALYSIS:");
        
        int[] subject1Scores = students.stream().mapToInt(s -> s.subject1).toArray();
        int[] subject2Scores = students.stream().mapToInt(s -> s.subject2).toArray();
        int[] subject3Scores = students.stream().mapToInt(s -> s.subject3).toArray();
        
        System.out.println("Subject 1 - Average: " + Arrays.stream(subject1Scores).average().orElse(0));
        System.out.println("Subject 2 - Average: " + Arrays.stream(subject2Scores).average().orElse(0));
        System.out.println("Subject 3 - Average: " + Arrays.stream(subject3Scores).average().orElse(0));
        
        // Count students scoring >60 in each subject
        long subject1Above60 = students.stream().filter(s -> s.subject1 > 60).count();
        long subject2Above60 = students.stream().filter(s -> s.subject2 > 60).count();
        long subject3Above60 = students.stream().filter(s -> s.subject3 > 60).count();
        
        System.out.println("Students >60 in Subject 1: " + subject1Above60);
        System.out.println("Students >60 in Subject 2: " + subject2Above60);
        System.out.println("Students >60 in Subject 3: " + subject3Above60);
    }
    
    private static void findTopPerformers(List<StudentRecord> students) {
        System.out.println("\n🏆 TOP PERFORMERS:");
        
        students.stream()
                .sorted((s1, s2) -> Integer.compare(s2.getTotalScore(), s1.getTotalScore()))
                .limit(3)
                .forEach(s -> System.out.println(s.name + " - Total: " + s.getTotalScore()));
    }
    
    private static void calculateClassStatistics(List<StudentRecord> students) {
        System.out.println("\n📊 CLASS STATISTICS:");
        
        double avgTotal = students.stream().mapToInt(StudentRecord::getTotalScore).average().orElse(0);
        int maxTotal = students.stream().mapToInt(StudentRecord::getTotalScore).max().orElse(0);
        int minTotal = students.stream().mapToInt(StudentRecord::getTotalScore).min().orElse(0);
        
        System.out.println("Class Average: " + avgTotal);
        System.out.println("Highest Total: " + maxTotal);
        System.out.println("Lowest Total: " + minTotal);
    }
    
    // Helper class for student data
    static class StudentRecord {
        String rollNo, name;
        int subject1, subject2, subject3;
        
        public StudentRecord(String rollNo, String name, int subject1, int subject2, int subject3) {
            this.rollNo = rollNo;
            this.name = name;
            this.subject1 = subject1;
            this.subject2 = subject2;
            this.subject3 = subject3;
        }
        
        public int getTotalScore() {
            return subject1 + subject2 + subject3;
        }
    }
}
```

### 📊 **Analysis Criteria**
- **Primary Filter:** Students with at least one subject score > 60
- **Secondary Filter:** Students with all subjects > 60
- **Statistical Analysis:** Class averages, top performers, subject-wise performance

---

## Practical 6: Web Page Object Counting

### **AIM**
Write a program using Selenium WebDriver to provide the total number of objects present or available on a web page. Perform object identification and counting.

### 🔧 **Tools Required**
- **Selenium WebDriver**
- **Java**
- **Firefox Browser**
- **GeckoDriver**

### 🚀 **Procedure**

#### 1. Basic Object Counting Implementation:

1. **WebDriver Setup for Object Counting**

```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.firefox.FirefoxDriver;
import java.util.List;

public class WebPageObjectCounter {
    
    private static WebDriver driver;
    
    public static void main(String[] args) {
        
        // Setup WebDriver
        System.setProperty("webdriver.gecko.driver", "path/to/geckodriver.exe");
        driver = new FirefoxDriver();
        
        try {
            // Navigate to target website
            driver.get("https://www.wikipedia.org");
            driver.manage().window().maximize();
            
            // Count different types of web elements
            countWebPageElements();
            
        } catch (Exception e) {
            System.err.println("Error during element counting: " + e.getMessage());
        } finally {
            driver.quit();
        }
    }
    
    private static void countWebPageElements() {
        
        System.out.println("🔍 WEB PAGE ELEMENT ANALYSIS");
        System.out.println("============================");
        
        // Count links
        List<WebElement> links = driver.findElements(By.tagName("a"));
        System.out.println("🔗 Total Links: " + links.size());
        
        // Print first 10 link texts
        System.out.println("\n📋 First 10 Links:");
        for (int i = 0; i < Math.min(10, links.size()); i++) {
            String linkText = links.get(i).getText().trim();
            String linkUrl = links.get(i).getAttribute("href");
            if (!linkText.isEmpty()) {
                System.out.println((i + 1) + ". " + linkText + " → " + linkUrl);
            }
        }
        
        // Count other elements
        countAdditionalElements();
    }
    
    private static void countAdditionalElements() {
        
        // Count images
        List<WebElement> images = driver.findElements(By.tagName("img"));
        System.out.println("\n🖼️ Total Images: " + images.size());
        
        // Count input fields
        List<WebElement> inputs = driver.findElements(By.tagName("input"));
        System.out.println("📝 Total Input Fields: " + inputs.size());
        
        // Count buttons
        List<WebElement> buttons = driver.findElements(By.tagName("button"));
        System.out.println("🔘 Total Buttons: " + buttons.size());
        
        // Count divs
        List<WebElement> divs = driver.findElements(By.tagName("div"));
        System.out.println("📦 Total Divs: " + divs.size());
        
        // Count spans
        List<WebElement> spans = driver.findElements(By.tagName("span"));
        System.out.println("📄 Total Spans: " + spans.size());
        
        // Count paragraphs
        List<WebElement> paragraphs = driver.findElements(By.tagName("p"));
        System.out.println("📰 Total Paragraphs: " + paragraphs.size());
        
        // Count headings
        countHeadings();
        
        // Count form elements
        countFormElements();
        
        // Calculate total elements
        calculateTotalElements();
    }
    
    private static void countHeadings() {
        int totalHeadings = 0;
        
        for (int i = 1; i <= 6; i++) {
            List<WebElement> headings = driver.findElements(By.tagName("h" + i));
            int count = headings.size();
            if (count > 0) {
                System.out.println("📑 H" + i + " Headings: " + count);
                totalHeadings += count;
            }
        }
        
        System.out.println("📊 Total Headings (H1-H6): " + totalHeadings);
    }
    
    private static void countFormElements() {
        System.out.println("\n📋 FORM ELEMENTS:");
        
        // Count forms
        List<WebElement> forms = driver.findElements(By.tagName("form"));
        System.out.println("📄 Total Forms: " + forms.size());
        
        // Count select dropdowns
        List<WebElement> selects = driver.findElements(By.tagName("select"));
        System.out.println("📋 Total Select Dropdowns: " + selects.size());
        
        // Count textareas
        List<WebElement> textareas = driver.findElements(By.tagName("textarea"));
        System.out.println("📝 Total Text Areas: " + textareas.size());
        
        // Count checkboxes
        List<WebElement> checkboxes = driver.findElements(By.cssSelector("input[type='checkbox']"));
        System.out.println("☑️ Total Checkboxes: " + checkboxes.size());
        
        // Count radio buttons
        List<WebElement> radioButtons = driver.findElements(By.cssSelector("input[type='radio']"));
        System.out.println("🔘 Total Radio Buttons: " + radioButtons.size());
    }
    
    private static void calculateTotalElements() {
        
        // Get all elements on the page
        List<WebElement> allElements = driver.findElements(By.xpath("//*"));
        
        System.out.println("\n🌐 TOTAL PAGE ANALYSIS:");
        System.out.println("============================");
        System.out.println("🔢 Total Elements on Page: " + allElements.size());
        
        // Calculate visible vs hidden elements
        long visibleElements = allElements.stream().filter(WebElement::isDisplayed).count();
        long hiddenElements = allElements.size() - visibleElements;
        
        System.out.println("👁️ Visible Elements: " + visibleElements);
        System.out.println("🙈 Hidden Elements: " + hiddenElements);
        
        // Get page title and URL
        System.out.println("\n📄 Page Information:");
        System.out.println("Title: " + driver.getTitle());
        System.out.println("URL: " + driver.getCurrentUrl());
    }
}
```

#### 2. Advanced Element Analysis:

2. **Comprehensive Element Analyzer**

```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.firefox.FirefoxDriver;
import java.util.*;

public class AdvancedElementAnalyzer {
    
    private static WebDriver driver;
    private static Map<String, Integer> elementCounts = new HashMap<>();
    
    public static void main(String[] args) {
        
        setupDriver();
        
        try {
            // Test multiple websites
            String[] testUrls = {
                "https://www.wikipedia.org",
                "https://www.github.com",
                "https://www.stackoverflow.com"
            };
            
            for (String url : testUrls) {
                analyzeWebsite(url);
                System.out.println("\n" + "=".repeat(50) + "\n");
            }
            
        } catch (Exception e) {
            System.err.println("Analysis error: " + e.getMessage());
        } finally {
            driver.quit();
        }
    }
    
    private static void setupDriver() {
        System.setProperty("webdriver.gecko.driver", "path/to/geckodriver.exe");
        driver = new FirefoxDriver();
        driver.manage().window().maximize();
    }
    
    private static void analyzeWebsite(String url) {
        
        System.out.println("🌐 ANALYZING: " + url);
        System.out.println("=" + "=".repeat(url.length() + 12));
        
        driver.get(url);
        
        // Wait for page to load
        try {
            Thread.sleep(3000);
        } catch (InterruptedException e) {
            Thread.currentThread().interrupt();
        }
        
        // Perform comprehensive analysis
        elementCounts.clear();
        countAllElementTypes();
        generateElementReport();
        analyzeInteractiveElements();
    }
    
    private static void countAllElementTypes() {
        
        // Define element types to count
        String[] elementTypes = {
            "a", "img", "div", "span", "p", "input", "button", "form",
            "h1", "h2", "h3", "h4", "h5", "h6", "ul", "ol", "li",
            "table", "tr", "td", "th", "select", "option", "textarea"
        };
        
        for (String elementType : elementTypes) {
            List<WebElement> elements = driver.findElements(By.tagName(elementType));
            elementCounts.put(elementType, elements.size());
        }
        
        // Count special elements
        elementCounts.put("checkbox", driver.findElements(By.cssSelector("input[type='checkbox']")).size());
        elementCounts.put("radio", driver.findElements(By.cssSelector("input[type='radio']")).size());
        elementCounts.put("submit", driver.findElements(By.cssSelector("input[type='submit']")).size());
    }
    
    private static void generateElementReport() {
        
        System.out.println("📊 ELEMENT COUNT REPORT:");
        System.out.println("-".repeat(25));
        
        // Sort elements by count (descending)
        elementCounts.entrySet().stream()
                .sorted(Map.Entry.<String, Integer>comparingByValue().reversed())
                .forEach(entry -> {
                    if (entry.getValue() > 0) {
                        System.out.printf("%-15s: %d%n", entry.getKey().toUpperCase(), entry.getValue());
                    }
                });
        
        // Calculate total
        int totalElements = elementCounts.values().stream().mapToInt(Integer::intValue).sum();
        System.out.println("-".repeat(25));
        System.out.println("TOTAL ELEMENTS: " + totalElements);
    }
    
    private static void analyzeInteractiveElements() {
        
        System.out.println("\n🎯 INTERACTIVE ELEMENTS ANALYSIS:");
        System.out.println("-".repeat(35));
        
        // Find clickable elements
        List<WebElement> clickableElements = driver.findElements(By.cssSelector("a, button, input[type='submit'], input[type='button']"));
        System.out.println("Clickable Elements: " + clickableElements.size());
        
        // Find form controls
        List<WebElement> formControls = driver.findElements(By.cssSelector("input, select, textarea"));
        System.out.println("Form Controls: " + formControls.size());
        
        // Find media elements
        List<WebElement> mediaElements = driver.findElements(By.cssSelector("img, video, audio"));
        System.out.println("Media Elements: " + mediaElements.size());
        
        // Analyze element attributes
        analyzeElementAttributes();
    }
    
    private static void analyzeElementAttributes() {
        
        System.out.println("\n🔍 ELEMENT ATTRIBUTES ANALYSIS:");
        System.out.println("-".repeat(32));
        
        // Count elements with IDs
        List<WebElement> elementsWithId = driver.findElements(By.xpath("//*[@id]"));
        System.out.println("Elements with ID: " + elementsWithId.size());
        
        // Count elements with classes
        List<WebElement> elementsWithClass = driver.findElements(By.xpath("//*[@class]"));
        System.out.println("Elements with Class: " + elementsWithClass.size());
        
        // Count elements with href (links)
        List<WebElement> elementsWithHref = driver.findElements(By.xpath("//*[@href]"));
        System.out.println("Elements with Href: " + elementsWithHref.size());
        
        // Count elements with src (images, scripts)
        List<WebElement> elementsWithSrc = driver.findElements(By.xpath("//*[@src]"));
        System.out.println("Elements with Src: " + elementsWithSrc.size());
    }
}
```

### 📊 **Expected Output Example**
```
🌐 ANALYZING: https://www.wikipedia.org
================================

📊 ELEMENT COUNT REPORT:
-------------------------
DIV            : 245
A              : 189
SPAN           : 156
IMG            : 45
P              : 32
INPUT          : 12
BUTTON         : 8
H1             : 5
H2             : 3
-------------------------
TOTAL ELEMENTS: 695

🎯 INTERACTIVE ELEMENTS ANALYSIS:
-----------------------------------
Clickable Elements: 205
Form Controls: 12
Media Elements: 45

🔍 ELEMENT ATTRIBUTES ANALYSIS:
--------------------------------
Elements with ID: 78
Elements with Class: 412
Elements with Href: 189
Elements with Src: 52
```

---

## Practical 7: Dropdown/Combo Box Analysis

### **AIM**
Write a program using Selenium WebDriver to get the number of items in a list or combo box on a web page. Perform element identification and counting.

### 🔧 **Tools Required**
- **Selenium WebDriver**
- **Java**
- **HTML Test Page** with `<select>` elements

### 🚀 **Procedure**

#### 1. Create Test HTML Page:

1. **Test HTML File (combo_test.html)**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Dropdown/Combo Box Test Page</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 20px; }
        select { margin: 10px; padding: 5px; font-size: 14px; }
        .container { margin: 20px 0; }
    </style>
</head>
<body>
    <h1>Dropdown/Combo Box Testing</h1>
    
    <!-- Country Selection -->
    <div class="container">
        <label for="country">Select Country:</label>
        <select id="country" name="country">
            <option value="">--Select Country--</option>
            <option value="us">United States</option>
            <option value="uk">United Kingdom</option>
            <option value="ca">Canada</option>
            <option value="au">Australia</option>
            <option value="in">India</option>
            <option value="de">Germany</option>
            <option value="fr">France</option>
            <option value="jp">Japan</option>
            <option value="br">Brazil</option>
            <option value="mx">Mexico</option>
        </select>
    </div>
    
    <!-- Programming Languages -->
    <div class="container">
        <label for="language">Programming Language:</label>
        <select id="language" name="language" multiple>
            <option value="java">Java</option>
            <option value="python">Python</option>
            <option value="javascript">JavaScript</option>
            <option value="csharp">C#</option>
            <option value="cpp">C++</option>
            <option value="php">PHP</option>
            <option value="ruby">Ruby</option>
            <option value="go">Go</option>
            <option value="swift">Swift</option>
            <option value="kotlin">Kotlin</option>
        </select>
    </div>
    
    <!-- Education Level -->
    <div class="container">
        <label for="education">Education Level:</label>
        <select id="education" name="education">
            <option value="high_school">High School</option>
            <option value="bachelor">Bachelor's Degree</option>
            <option value="master">Master's Degree</option>
            <option value="phd">PhD</option>
            <option value="diploma">Diploma</option>
        </select>
    </div>
    
    <!-- Years of Experience -->
    <div class="container">
        <label for="experience">Years of Experience:</label>
        <select id="experience" name="experience">
            <option value="0-1">0-1 years</option>
            <option value="2-5">2-5 years</option>
            <option value="6-10">6-10 years</option>
            <option value="11-15">11-15 years</option>
            <option value="16+">16+ years</option>
        </select>
    </div>
</body>
</html>
```

#### 2. Java Implementation for Dropdown Analysis:

2. **Complete Dropdown Analyzer**

```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.support.ui.Select;
import java.util.List;

public class DropdownAnalyzer {
    
    private static WebDriver driver;
    
    public static void main(String[] args) {
        
        // Setup WebDriver
        System.setProperty("webdriver.gecko.driver", "path/to/geckodriver.exe");
        driver = new FirefoxDriver();
        
        try {
            // Load test HTML page
            String htmlFilePath = "file:///path/to/combo_test.html";
            driver.get(htmlFilePath);
            driver.manage().window().maximize();
            
            // Analyze all dropdowns on the page
            analyzeAllDropdowns();
            
        } catch (Exception e) {
            System.err.println("Error during dropdown analysis: " + e.getMessage());
            e.printStackTrace();
        } finally {
            driver.quit();
        }
    }
    
    private static void analyzeAllDropdowns() {
        
        System.out.println("🔍 DROPDOWN/COMBO BOX ANALYSIS");
        System.out.println("===============================");
        
        // Define dropdown IDs to analyze
        String[] dropdownIds = {"country", "language", "education", "experience"};
        
        for (String dropdownId : dropdownIds) {
            analyzeDropdown(dropdownId);
            System.out.println("-".repeat(40));
        }
        
        // Summary analysis
        generateSummaryReport();
    }
    
    private static void analyzeDropdown(String dropdownId) {
        
        try {
            // Find dropdown element
            WebElement dropdownElement = driver.findElement(By.id(dropdownId));
            Select dropdown = new Select(dropdownElement);
            
            // Get all options
            List<WebElement> options = dropdown.getOptions();
            int optionCount = options.size();
            
            // Display dropdown information
            System.out.println("📋 Dropdown: " + dropdownId.toUpperCase());
            System.out.println("Total Options: " + optionCount);
            
            // Check if multiple selection is allowed
            boolean isMultiple = dropdown.isMultiple();
            System.out.println("Multiple Selection: " + (isMultiple ? "Yes" : "No"));
            
            // List all options
            System.out.println("Options List:");
            for (int i = 0; i < options.size(); i++) {
                WebElement option = options.get(i);
                String optionText = option.getText();
                String optionValue = option.getAttribute("value");
                boolean isSelected = option.isSelected();
                
                System.out.printf("%d. Text: %-20s Value: %-15s Selected: %s%n", 
                    (i + 1), optionText, optionValue, isSelected ? "Yes" : "No");
            }
            
            // Test dropdown interactions
            testDropdownInteractions(dropdown, dropdownId);
            
        } catch (Exception e) {
            System.err.println("Error analyzing dropdown " + dropdownId + ": " + e.getMessage());
        }
    }
    
    private static void testDropdownInteractions(Select dropdown, String dropdownId) {
        
        System.out.println("\n🎯 Testing Interactions:");
        
        try {
            // Test selecting by index
            if (dropdown.getOptions().size() > 1) {
                dropdown.selectByIndex(1);
                WebElement selectedOption = dropdown.getFirstSelectedOption();
                System.out.println("Selected by Index (1): " + selectedOption.getText());
            }
            
            // Test selecting by value (if available)
            List<WebElement> options = dropdown.getOptions();
            if (options.size() > 2) {
                String testValue = options.get(2).getAttribute("value");
                if (!testValue.isEmpty()) {
                    dropdown.selectByValue(testValue);
                    WebElement selectedOption = dropdown.getFirstSelectedOption();
                    System.out.println("Selected by Value (" + testValue + "): " + selectedOption.getText());
                }
            }
            
            // Test selecting by visible text
            if (options.size() > 3) {
                String testText = options.get(3).getText();
                dropdown.selectByVisibleText(testText);
                WebElement selectedOption = dropdown.getFirstSelectedOption();
                System.out.println("Selected by Text: " + selectedOption.getText());
            }
            
            // For multiple select dropdowns, test multiple selections
            if (dropdown.isMultiple() && options.size() >= 3) {
                dropdown.selectByIndex(0);
                dropdown.selectByIndex(1);
                dropdown.selectByIndex(2);
                
                List<WebElement> selectedOptions = dropdown.getAllSelectedOptions();
                System.out.println("Multiple Selections (" + selectedOptions.size() + " items):");
                for (WebElement option : selectedOptions) {
                    System.out.println("  - " + option.getText());
                }
                
                // Deselect all
                dropdown.deselectAll();
                System.out.println("All options deselected");
            }
            
        } catch (Exception e) {
            System.err.println("Error testing interactions: " + e.getMessage());
        }
    }
    
    private static void generateSummaryReport() {
        
        System.out.println("\n📊 SUMMARY REPORT");
        System.out.println("==================");
        
        // Find all select elements on page
        List<WebElement> allDropdowns = driver.findElements(By.tagName("select"));
        System.out.println("Total Dropdowns on Page: " + allDropdowns.size());
        
        int totalOptions = 0;
        int multipleSelectionCount = 0;
        
        for (WebElement dropdownElement : allDropdowns) {
            Select dropdown = new Select(dropdownElement);
            List<WebElement> options = dropdown.getOptions();
            totalOptions += options.size();
            
            if (dropdown.isMultiple()) {
                multipleSelectionCount++;
            }
        }
        
        System.out.println("Total Options Across All Dropdowns: " + totalOptions);
        System.out.println("Dropdowns with Multiple Selection: " + multipleSelectionCount);
        System.out.println("Single Selection Dropdowns: " + (allDropdowns.size() - multipleSelectionCount));
        
        // Calculate average options per dropdown
        double averageOptions = totalOptions / (double) allDropdowns.size();
        System.out.printf("Average Options per Dropdown: %.2f%n", averageOptions);
    }
}
```

#### 3. Enhanced Dropdown Testing:

3. **Advanced Dropdown Testing with Validation**

```java
import org.openqa.selenium.support.ui.Select;
import org.testng.annotations.Test;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.AfterClass;
import org.testng.Assert;

public class AdvancedDropdownTesting {
    
    private WebDriver driver;
    
    @BeforeClass
    public void setUp() {
        System.setProperty("webdriver.gecko.driver", "path/to/geckodriver.exe");
        driver = new FirefoxDriver();
        driver.get("file:///path/to/combo_test.html");
    }
    
    @Test
    public void testCountryDropdown() {
        Select countryDropdown = new Select(driver.findElement(By.id("country")));
        List<WebElement> options = countryDropdown.getOptions();
        
        // Verify expected number of options (including placeholder)
        Assert.assertEquals(options.size(), 11, "Country dropdown should have 11 options");
        
        // Verify first option is placeholder
        Assert.assertEquals(options.get(0).getText(), "--Select Country--");
        
        // Test selection functionality
        countryDropdown.selectByValue("us");
        WebElement selected = countryDropdown.getFirstSelectedOption();
        Assert.assertEquals(selected.getText(), "United States");
        
        System.out.println("✅ Country dropdown test passed");
    }
    
    @Test
    public void testLanguageDropdown() {
        Select languageDropdown = new Select(driver.findElement(By.id("language")));
        List<WebElement> options = languageDropdown.getOptions(); 
        
        // Verify it's a multiple selection dropdown
        Assert.assertTrue(languageDropdown.isMultiple(), "Language dropdown should allow multiple selections");
        
        // Verify number of options
        Assert.assertEquals(options.size(), 10, "Language dropdown should have 10 options");
        
        // Test multiple selections
        languageDropdown.selectByValue("java");
        languageDropdown.selectByValue("python");
        languageDropdown.selectByValue("javascript");
        
        List<WebElement> selectedOptions = languageDropdown.getAllSelectedOptions();
        Assert.assertEquals(selectedOptions.size(), 3, "Should have 3 selected options");
        
        System.out.println("✅ Language dropdown test passed");
    }
    
    @Test
    public void testEducationDropdown() {
        Select educationDropdown = new Select(driver.findElement(By.id("education")));
        List<WebElement> options = educationDropdown.getOptions();
        
        // Verify single selection
        Assert.assertFalse(educationDropdown.isMultiple(), "Education dropdown should be single selection");
        
        // Verify option count
        Assert.assertEquals(options.size(), 5, "Education dropdown should have 5 options");
        
        // Test each option
        for (int i = 0; i < options.size(); i++) {
            educationDropdown.selectByIndex(i);
            WebElement selected = educationDropdown.getFirstSelectedOption();
            Assert.assertEquals(selected, options.get(i), "Selected option should match expected");
        }
        
        System.out.println("✅ Education dropdown test passed");
    }
    
    @Test
    public void testExperienceDropdown() {
        Select experienceDropdown = new Select(driver.findElement(By.id("experience")));
        List<WebElement> options = experienceDropdown.getOptions();
        
        Assert.assertEquals(options.size(), 5, "Experience dropdown should have 5 options");
        
        // Verify all options have proper text
        String[] expectedTexts = {"0-1 years", "2-5 years", "6-10 years", "11-15 years", "16+ years"};
        for (int i = 0; i < expectedTexts.length; i++) {
            Assert.assertEquals(options.get(i).getText(), expectedTexts[i]);
        }
        
        System.out.println("✅ Experience dropdown test passed");
    }
    
    @AfterClass
    public void tearDown() {
        if (driver != null) {
            driver.quit();
        }
    }
}
```

### 📊 **Expected Output**
```
🔍 DROPDOWN/COMBO BOX ANALYSIS
===============================
📋 Dropdown: COUNTRY
Total Options: 11
Multiple Selection: No
Options List:
1. Text: --Select Country--    Value:               Selected: No
2. Text: United States         Value: us            Selected: No
3. Text: United Kingdom        Value: uk            Selected: No
...

🎯 Testing Interactions:
Selected by Index (1): United States
Selected by Value (uk): United Kingdom
Selected by Text: Canada

----------------------------------------

📊 SUMMARY REPORT
==================
Total Dropdowns on Page: 4
Total Options Across All Dropdowns: 31
Dropdowns with Multiple Selection: 1
Single Selection Dropdowns: 3
Average Options per Dropdown: 7.75
```

---

## Practical 8: Checkbox State Analysis

### **AIM**
Write a program using Selenium WebDriver to count the number of checkboxes on a web page, including checked and unchecked counts. Perform checkbox identification and counting.

### 🔧 **Tools Required**
- **Selenium WebDriver**
- **Java**
- **HTML Test Page** with checkboxes

### 🚀 **Procedure**

#### 1. Create Test HTML Page:

1. **Checkbox Test HTML (checkbox_test.html)**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Checkbox Testing Page</title>
    <style>
        body { 
            font-family: Arial, sans-serif; 
            margin: 20px; 
            line-height: 1.6;
        }
        .section { 
            margin: 20px 0; 
            padding: 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        .checkbox-item { 
            margin: 8px 0; 
        }
        h2 { color: #333; }
        label { cursor: pointer; }
    </style>
</head>
<body>
    <h1>Checkbox State Analysis Test Page</h1>
    
    <!-- Programming Skills Section -->
    <div class="section">
        <h2>Programming Skills</h2>
        <div class="checkbox-item">
            <input type="checkbox" id="java" name="skills" value="java" checked>
            <label for="java">Java</label>
        </div>
        <div class="checkbox-item">
            <input type="checkbox" id="python" name="skills" value="python" checked>
            <label for="python">Python</label>
        </div>
        <div class="checkbox-item">
            <input type="checkbox" id="javascript" name="skills" value="javascript">
            <label for="javascript">JavaScript</label>
        </div>
        <div class="checkbox-item">
            <input type="checkbox" id="csharp" name="skills" value="csharp">
            <label for="csharp">C#</label>
        </div>
        <div class="checkbox-item">
            <input type="checkbox" id="php" name="skills" value="php" checked>
            <label for="php">PHP</label>
        </div>
    </div>
    
    <!-- Interests Section -->
    <div class="section">
        <h2>Areas of Interest</h2>
        <div class="checkbox-item">
            <input type="checkbox" id="webdev" name="interests" value="webdev" checked>
            <label for="webdev">Web Development</label>
        </div>
        <div class="checkbox-item">
            <input type="checkbox" id="mobile" name="interests" value="mobile">
            <label for="mobile">Mobile Development</label>
        </div>
        <div class="checkbox-item">
            <input type="checkbox" id="ai" name="interests" value="ai">
            <label for="ai">Artificial Intelligence</label>
        </div>
        <div class="checkbox-item">
            <input type="checkbox" id="cybersecurity" name="interests" value="cybersecurity" checked>
            <label for="cybersecurity">Cybersecurity</label>
        </div>
    </div>
    
    <!-- Technologies Section -->
    <div class="section">
        <h2>Technologies Used</h2>
        <div class="checkbox-item">
            <input type="checkbox" id="react" name="technologies" value="react">
            <label for="react">React</label>
        </div>
        <div class="checkbox-item">
            <input type="checkbox" id="angular" name="technologies" value="angular">
            <label for="angular">Angular</label>
        </div>
        <div class="checkbox-item">
            <input type="checkbox" id="vue" name="technologies" value="vue" checked>
            <label for="vue">Vue.js</label>
        </div>
        <div class="checkbox-item">
            <input type="checkbox" id="nodejs" name="technologies" value="nodejs">
            <label for="nodejs">Node.js</label>
        </div>
        <div class="checkbox-item">
            <input type="checkbox" id="docker" name="technologies" value="docker">
            <label for="docker">Docker</label>
        </div>
    </div>
    
    <!-- Preferences Section -->
    <div class="section">
        <h2>Work Preferences</h2>
        <div class="checkbox-item">
            <input type="checkbox" id="remote" name="preferences" value="remote" checked>
            <label for="remote">Remote Work</label>
        </div>
        <div class="checkbox-item">
            <input type="checkbox" id="flexible" name="preferences" value="flexible" checked>
            <label for="flexible">Flexible Hours</label>
        </div>
        <div class="checkbox-item">
            <input type="checkbox" id="team" name="preferences" value="team">
            <label for="team">Team Collaboration</label>
        </div>
    </div>
</body>
</html>
```

#### 2. Basic Checkbox Analysis:

2. **Simple Checkbox Counter**

```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.firefox.FirefoxDriver;
import java.util.List;

public class CheckboxAnalyzer {
    
    private static WebDriver driver;
    
    public static void main(String[] args) {
        
        // Setup WebDriver
        System.setProperty("webdriver.gecko.driver", "path/to/geckodriver.exe");
        driver = new FirefoxDriver();
        
        try {
            // Load test HTML page
            String htmlFilePath = "file:///path/to/checkbox_test.html";
            driver.get(htmlFilePath);
            driver.manage().window().maximize();
            
            // Perform checkbox analysis
            analyzeCheckboxes();
            
        } catch (Exception e) {
            System.err.println("Error during checkbox analysis: " + e.getMessage());
            e.printStackTrace();
        } finally {
            driver.quit();
        }
    }
    
    private static void analyzeCheckboxes() {
        
        System.out.println("☑️ CHECKBOX STATE ANALYSIS");
        System.out.println("===========================");
        
        // Find all checkboxes on the page
        List<WebElement> allCheckboxes = driver.findElements(By.cssSelector("input[type='checkbox']"));
        
        int totalCheckboxes = allCheckboxes.size();
        int checkedCount = 0;
        int uncheckedCount = 0;
        
        System.out.println("📊 Total Checkboxes Found: " + totalCheckboxes);
        System.out.println("\n📋 Checkbox Details:");
        System.out.println("-".repeat(50));
        
        // Analyze each checkbox
        for (int i = 0; i < allCheckboxes.size(); i++) {
            WebElement checkbox = allCheckboxes.get(i);
            
            String id = checkbox.getAttribute("id");
            String name = checkbox.getAttribute("name");
            String value = checkbox.getAttribute("value");
            boolean isSelected = checkbox.isSelected();
            boolean isEnabled = checkbox.isEnabled();
            boolean isDisplayed = checkbox.isDisplayed();
            
            // Get associated label text
            String labelText = getLabelText(id);
            
            // Count checked/unchecked
            if (isSelected) {
                checkedCount++;
            } else {
                uncheckedCount++;
            }
            
            // Display checkbox information
            System.out.printf("%d. ID: %-12s | Name: %-12s | Value: %-12s%n", 
                (i + 1), id, name, value);
            System.out.printf("   Label: %-20s | Checked: %-5s | Enabled: %-5s | Visible: %s%n", 
                labelText, isSelected, isEnabled, isDisplayed);
            System.out.println();
        }
        
        // Display summary
        displaySummary(totalCheckboxes, checkedCount, uncheckedCount);
        
        // Analyze by groups
        analyzeCheckboxGroups();
    }
    
    private static String getLabelText(String checkboxId) {
        try {
            WebElement label = driver.findElement(By.cssSelector("label[for='" + checkboxId + "']"));
            return label.getText();
        } catch (Exception e) {
            return "No Label";
        }
    }
    
    private static void displaySummary(int total, int checked, int unchecked) {
        
        System.out.println("📈 SUMMARY STATISTICS");
        System.out.println("=====================");
        System.out.println("Total Checkboxes: " + total);
        System.out.println("✅ Checked: " + checked);
        System.out.println("⬜ Unchecked: " + unchecked);
        
        if (total > 0) {
            double checkedPercentage = (checked / (double) total) * 100;
            double uncheckedPercentage = (unchecked / (double) total) * 100;
            
            System.out.printf("Checked Percentage: %.1f%%%n", checkedPercentage);
            System.out.printf("Unchecked Percentage: %.1f%%%n", uncheckedPercentage);
        }
        
        System.out.println();
    }
    
    private static void analyzeCheckboxGroups() {
        
        System.out.println("👥 GROUP-WISE ANALYSIS");
        System.out.println("======================");
        
        // Define groups to analyze
        String[] groups = {"skills", "interests", "technologies", "preferences"};
        
        for (String group : groups) {
            analyzeCheckboxGroup(group);
        }
    }
    
    private static void analyzeCheckboxGroup(String groupName) {
        
        try {
            List<WebElement> groupCheckboxes = driver.findElements(
                By.cssSelector("input[type='checkbox'][name='" + groupName + "']")
            );
            
            if (groupCheckboxes.isEmpty()) {
                return;
            }
            
            int totalInGroup = groupCheckboxes.size();
            int checkedInGroup = 0;
            
            System.out.println("Group: " + groupName.toUpperCase());
            
            for (WebElement checkbox : groupCheckboxes) {
                String id = checkbox.getAttribute("id");
                String labelText = getLabelText(id);
                boolean isChecked = checkbox.isSelected();
                
                if (isChecked) {
                    checkedInGroup++;
                }
                
                System.out.printf("  - %-20s: %s%n", labelText, isChecked ? "✅" : "⬜");
            }
            
            System.out.printf("  Summary: %d/%d checked (%.1f%%)%n%n", 
                checkedInGroup, totalInGroup, (checkedInGroup / (double) totalInGroup) * 100);
            
        } catch (Exception e) {
            System.err.println("Error analyzing group " + groupName + ": " + e.getMessage());
        }
    }
}
```

#### 3. Advanced Checkbox Testing:

3. **Interactive Checkbox Testing**

```java
import org.openqa.selenium.interactions.Actions;
import org.testng.annotations.Test;
import org.testng.Assert;

public class AdvancedCheckboxTesting {
    
    private WebDriver driver;
    
    @Test
    public void testCheckboxInteractions() {
        
        setupDriver();
        
        try {
            driver.get("file:///path/to/checkbox_test.html");
            
            // Test individual checkbox operations
            testIndividualCheckboxes();
            
            // Test group operations
            testGroupOperations();
            
            // Test state persistence
            testStatePersistence();
            
        } finally {
            driver.quit();
        }
    }
    
    private void testIndividualCheckboxes() {
        
        System.out.println("🔍 Testing Individual Checkbox Operations");
        
        // Test checking unchecked boxes
        WebElement jsCheckbox = driver.findElement(By.id("javascript"));
        Assert.assertFalse(jsCheckbox.isSelected(), "JavaScript checkbox should be unchecked initially");
        
        jsCheckbox.click();
        Assert.assertTrue(jsCheckbox.isSelected(), "JavaScript checkbox should be checked after click");
        
        // Test unchecking checked boxes
        WebElement javaCheckbox = driver.findElement(By.id("java"));
        Assert.assertTrue(javaCheckbox.isSelected(), "Java checkbox should be checked initially");
        
        javaCheckbox.click();
        Assert.assertFalse(javaCheckbox.isSelected(), "Java checkbox should be unchecked after click");
        
        System.out.println("✅ Individual checkbox tests passed");
    }
    
    private void testGroupOperations() {
        
        System.out.println("🔍 Testing Group Operations");
        
        // Select all checkboxes in a group
        List<WebElement> techCheckboxes = driver.findElements(
            By.cssSelector("input[name='technologies']"));
        
        int initialChecked = 0;
        for (WebElement checkbox : techCheckboxes) {
            if (checkbox.isSelected()) {
                initialChecked++;
            }
        }
        
        // Check all unchecked boxes in the group
        for (WebElement checkbox : techCheckboxes) {
            if (!checkbox.isSelected()) {
                checkbox.click();
            }
        }
        
        // Verify all are now checked
        for (WebElement checkbox : techCheckboxes) {
            Assert.assertTrue(checkbox.isSelected(), "All technology checkboxes should be checked");
        }
        
        System.out.println("✅ Group operations tests passed");
    }
    
    private void testStatePersistence() {
        
        System.out.println("🔍 Testing State Persistence");
        
        // Record initial states
        List<WebElement> allCheckboxes = driver.findElements(By.cssSelector("input[type='checkbox']"));
        boolean[] initialStates = new boolean[allCheckboxes.size()];
        
        for (int i = 0; i < allCheckboxes.size(); i++) {
            initialStates[i] = allCheckboxes.get(i).isSelected();
        }
        
        // Perform some interactions
        allCheckboxes.get(0).click();
        allCheckboxes.get(2).click();
        allCheckboxes.get(4).click();
        
        // Refresh page
        driver.navigate().refresh();
        
        // Check if states are restored (they should revert to HTML defaults)
        List<WebElement> refreshedCheckboxes = driver.findElements(By.cssSelector("input[type='checkbox']"));
        
        for (int i = 0; i < refreshedCheckboxes.size(); i++) {
            // After refresh, should match original HTML state, not modified state
            boolean currentState = refreshedCheckboxes.get(i).isSelected();
            System.out.printf("Checkbox %d: Initial=%s, Current=%s%n", 
                i+1, initialStates[i], currentState);
        }
        
        System.out.println("✅ State persistence tests completed");
    }
    
    private void setupDriver() {
        System.setProperty("webdriver.gecko.driver", "path/to/geckodriver.exe");
        driver = new FirefoxDriver();
        driver.manage().window().maximize();
    }
}
```

#### 4. Comprehensive Checkbox Report Generator:

4. **Detailed Checkbox Report**

```java
import java.util.*;

public class CheckboxReportGenerator {
    
    private WebDriver driver;
    
    public void generateComprehensiveReport() {
        
        System.out.println("📊 COMPREHENSIVE CHECKBOX ANALYSIS REPORT");
        System.out.println("==========================================");
        
        // Overall statistics
        generateOverallStatistics();
        
        // Group analysis
        generateGroupAnalysis();
        
        // Accessibility analysis
        generateAccessibilityReport();
        
        // Visual analysis
        generateVisualAnalysisReport();
    }
    
    private void generateOverallStatistics() {
        
        List<WebElement> allCheckboxes = driver.findElements(By.cssSelector("input[type='checkbox']"));
        
        Map<String, Integer> statistics = new HashMap<>();
        statistics.put("total", allCheckboxes.size());
        statistics.put("checked", 0);
        statistics.put("unchecked", 0);
        statistics.put("enabled", 0);
        statistics.put("disabled", 0);
        statistics.put("visible", 0);
        statistics.put("hidden", 0);
        
        for (WebElement checkbox : allCheckboxes) {
            if (checkbox.isSelected()) statistics.put("checked", statistics.get("checked") + 1);
            else statistics.put("unchecked", statistics.get("unchecked") + 1);
            
            if (checkbox.isEnabled()) statistics.put("enabled", statistics.get("enabled") + 1);
            else statistics.put("disabled", statistics.get("disabled") + 1);
            
            if (checkbox.isDisplayed()) statistics.put("visible", statistics.get("visible") + 1);
            else statistics.put("hidden", statistics.get("hidden") + 1);
        }
        
        System.out.println("📈 OVERALL STATISTICS:");
        statistics.forEach((key, value) -> 
            System.out.printf("%-12s: %d%n", key.toUpperCase(), value));
    }
    
    private void generateGroupAnalysis() {
        
        System.out.println("\n👥 GROUP ANALYSIS:");
        
        // Find unique group names
        List<WebElement> allCheckboxes = driver.findElements(By.cssSelector("input[type='checkbox']"));
        Set<String> groups = new HashSet<>();
        
        for (WebElement checkbox : allCheckboxes) {
            String name = checkbox.getAttribute("name");
            if (name != null && !name.isEmpty()) {
                groups.add(name);
            }
        }
        
        for (String group : groups) {
            List<WebElement> groupCheckboxes = driver.findElements(
                By.cssSelector("input[name='" + group + "']"));
            
            long checkedInGroup = groupCheckboxes.stream().filter(WebElement::isSelected).count();
            
            System.out.printf("Group %-15s: %d total, %d checked (%.1f%%)%n", 
                group, groupCheckboxes.size(), checkedInGroup, 
                (checkedInGroup / (double) groupCheckboxes.size()) * 100);
        }
    }
    
    private void generateAccessibilityReport() {
        
        System.out.println("\n♿ ACCESSIBILITY ANALYSIS:");
        
        List<WebElement> allCheckboxes = driver.findElements(By.cssSelector("input[type='checkbox']"));
        int withLabels = 0;
        int withoutLabels = 0;
        int withAriaLabels = 0;
        
        for (WebElement checkbox : allCheckboxes) {
            String id = checkbox.getAttribute("id");
            String ariaLabel = checkbox.getAttribute("aria-label");
            
            boolean hasLabel = false;
            if (id != null && !id.isEmpty()) {
                try {
                    driver.findElement(By.cssSelector("label[for='" + id + "']"));
                    hasLabel = true;
                    withLabels++;
                } catch (Exception e) {
                    // No label found
                }
            }
            
            if (!hasLabel) {
                withoutLabels++;
            }  
            
            if (ariaLabel != null && !ariaLabel.isEmpty()) {
                withAriaLabels++;
            }
        }
        
        System.out.println("Checkboxes with labels: " + withLabels);
        System.out.println("Checkboxes without labels: " + withoutLabels);
        System.out.println("Checkboxes with aria-labels: " + withAriaLabels);
        
        if (withoutLabels > 0) {
            System.out.println("⚠️ Warning: Some checkboxes lack proper labeling for accessibility");
        }
    }
    
    private void generateVisualAnalysisReport() {
        
        System.out.println("\n👁️ VISUAL ANALYSIS:");
        
        List<WebElement> allCheckboxes = driver.findElements(By.cssSelector("input[type='checkbox']"));
        
        for (WebElement checkbox : allCheckboxes) {
            String id = checkbox.getAttribute("id");
            
            // Get position and size
            org.openqa.selenium.Point location = checkbox.getLocation();
            org.openqa.selenium.Dimension size = checkbox.getSize();
            
            System.out.printf("Checkbox %-12s: Position(%d,%d), Size(%dx%d)%n", 
                id, location.getX(), location.getY(), size.getWidth(), size.getHeight());
        }
    }
}
```

### 📊 **Expected Output**
```
☑️ CHECKBOX STATE ANALYSIS
===========================
📊 Total Checkboxes Found: 17

📋 Checkbox Details:
--------------------------------------------------
1. ID: java         | Name: skills      | Value: java        
   Label: Java                | Checked: true  | Enabled: true  | Visible: true

2. ID: python       | Name: skills      | Value: python      
   Label: Python              | Checked: true  | Enabled: true  | Visible: true

📈 SUMMARY STATISTICS
=====================
Total Checkboxes: 17
✅ Checked: 7
⬜ Unchecked: 10
Checked Percentage: 41.2%
Unchecked Percentage: 58.8%

👥 GROUP-WISE ANALYSIS
======================
Group: SKILLS
  - Java                 : ✅
  - Python               : ✅
  - JavaScript           : ⬜
  - C#                   : ⬜
  - PHP                  : ✅
  Summary: 3/5 checked (60.0%)
```

---

## 🛠️ **Prerequisites and System Requirements**

### **Software Requirements:**
- **Java Development Kit (JDK)** 8 or higher
- **Selenium WebDriver** (latest version)
- **Web Browsers:** Firefox, Chrome, Edge
- **Browser Drivers:** GeckoDriver (Firefox), ChromeDriver (Chrome)
- **IDE:** Eclipse, IntelliJ IDEA, NetBeans
- **Build Tools:** Maven or Gradle (optional)

### **Essential Dependencies:**
```xml
<!-- Maven Dependencies -->
<dependencies>
    <dependency>
        <groupId>org.seleniumhq.selenium</groupId>
        <artifactId>selenium-java</artifactId>
        <version>4.15.0</version>
    </dependency>
    <dependency>
        <groupId>org.testng</groupId>
        <artifactId>testng</artifactId>
        <version>7.8.0</version>
    </dependency>
    <dependency>
        <groupId>net.sourceforge.jexcelapi</groupId>
        <artifactId>jxl</artifactId>
        <version>2.6.12</version>
    </dependency>
</dependencies>
```

### **Environment Setup:**
```bash
# Download WebDriver executables
# Firefox GeckoDriver: https://github.com/mozilla/geckodriver/releases
# Chrome ChromeDriver: https://chromedriver.chromium.org/

# Set system properties in Java code
System.setProperty("webdriver.gecko.driver", "/path/to/geckodriver");
System.setProperty("webdriver.chrome.driver", "/path/to/chromedriver");
```

---

## 📚 **Best Practices and Guidelines**

### **Test Automation Best Practices:**
1. **Page Object Model (POM)** - Separate page elements from test logic
2. **Data-Driven Testing** - Use external data sources for test inputs
3. **Explicit Waits** - Use WebDriverWait instead of Thread.sleep()
4. **Error Handling** - Implement try-catch blocks for robust tests
5. **Test Independence** - Each test should be able to run independently

### **Selenium WebDriver Guidelines:**
- **Driver Management:** Always close drivers in finally blocks
- **Element Location:** Use reliable locators (ID > CSS > XPath)
- **Synchronization:** Wait for elements before interaction
- **Cross-Browser Testing:** Test across multiple browsers
- **Headless Execution:** Use headless mode for CI/CD pipelines

### **Code Organization:**
```java
// Recommended project structure
src/
├── main/java/
│   ├── pages/          // Page Object Model classes
│   ├── utils/          // Utility classes
│   └── data/           // Test data classes
└── test/java/
    ├── tests/          // Test classes
    └── resources/      // Test resources (HTML files, data files)
```

---

## 🔗 **Additional Resources**

### **Documentation:**
- [Selenium Documentation](https://selenium-python.readthedocs.io/)
- [TestNG Documentation](https://testng.org/doc/)
- [WebDriver API Reference](https://selenium.dev/selenium/docs/api/java/)

### **Testing Tools:**
- **Selenium Grid** - Distributed test execution
- **Appium** - Mobile application testing
- **BrowserStack/Sauce Labs** - Cloud-based testing platforms
- **Jenkins** - Continuous Integration for automated testing

### **Learning Resources:**
- [Selenium Tutorial](https://www.selenium.dev/documentation/)
- [TestNG Tutorial](https://www.tutorialspoint.com/testng/)
- [Java Excel API (JXL) Guide](http://jexcelapi.sourceforge.net/)

---

## 📄 **License and Disclaimer**

**Educational Use:** This material is provided for educational purposes in software testing and quality assurance.

**Tool Versions:** Ensure compatibility between Selenium WebDriver versions and browser versions.

**Browser Updates:** Regular browser updates may require corresponding WebDriver updates.

---

*Software testing is a critical aspect of software development. These practical exercises provide hands-on experience with industry-standard automation tools and techniques.*

**Last Updated:** October 2024
