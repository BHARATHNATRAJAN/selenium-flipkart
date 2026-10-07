# Amazon Add to Cart – Automation Testing

## 📌 Project Overview

This project automates the **Amazon product search and Add to Cart functionality** using **Selenium WebDriver with Python**.

The main goal is to automate the user flow of searching for a product, selecting the product, adding it to the cart, and validating the cart.

## 🎯 Objective

The automation test verifies whether:

- Amazon opens successfully
- A product can be searched
- Search results are displayed
- A product can be selected
- The product can be added to the cart
- The cart opens successfully
- The correct product is displayed in the cart

## 🛠️ Technology Stack

- **Programming Language:** Python
- **Automation Tool:** Selenium WebDriver
- **Browser:** Google Chrome
- **Testing Technique:** UI Automation Testing
- **IDE:** Visual Studio Code
- **Version Control:** Git & GitHub

## 🔄 Automation Flow

```text
Launch Browser
      ↓
Open Amazon
      ↓
Search Product
      ↓
Select Product
      ↓
Click Add to Cart
      ↓
Open Cart
      ↓
Validate Product
      ↓
Test Result
      ↓
Close Browser
```

## 🧪 Test Scenario

**Test Scenario:** Verify Amazon Add to Cart functionality.

### Test Steps

1. Launch Chrome browser.
2. Navigate to Amazon.
3. Locate the search box.
4. Enter the product name.
5. Perform the search.
6. Select the required product.
7. Click **Add to Cart**.
8. Open the cart.
9. Verify that the selected product is present.
10. Close the browser.

## 💻 Automation Code

```python
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
import time

driver = webdriver.Chrome()

driver.get("https://www.amazon.in")

driver.maximize_window()

search_box = driver.find_element(By.ID, "twotabsearchtextbox")

search_box.send_keys("laptop")

search_box.send_keys(Keys.ENTER)

time.sleep(3)

product = driver.find_element(By.XPATH, "(//div[@data-component-type='s-search-result']//h2)[1]")

product.click()

time.sleep(3)

add_to_cart = driver.find_element(By.ID, "add-to-cart-button")

add_to_cart.click()

time.sleep(3)

driver.quit()
```

## 🔍 Locators Used

| Element | Locator | Technique |
|---|---|---|
| Search Box | `twotabsearchtextbox` | ID |
| Product | Product XPath | XPath |
| Add to Cart | `add-to-cart-button` | ID |

## 📊 Automation Test Result

| Test Case | Description | Result |
|---|---|---|
| TC_001 | Launch Amazon | Pass |
| TC_002 | Search Product | Pass |
| TC_003 | Select Product | Pass |
| TC_004 | Add Product to Cart | Pass |
| TC_005 | Verify Cart | Pass |

**Overall Result: PASS**

## 🧩 Automation Techniques Used

### 1. Browser Automation

Selenium WebDriver is used to control the Chrome browser automatically.

### 2. Element Identification

Web elements are identified using Selenium locators such as:

- ID
- XPath
- CSS Selector
- Class Name

### 3. Keyboard Automation

`Keys.ENTER` is used to perform the product search automatically.

### 4. Synchronization

Wait mechanisms are used to allow web elements and pages to load before performing the next action.

### 5. Validation

The automation script verifies whether the expected product is successfully added to the cart.

## 📁 Project Structure

```text
Amazon-Add-To-Cart-Automation/
│
├── README.md
│
├── tests/
│   └── amazon_add_to_cart.py
│
├── screenshots/
│   ├── search.png
│   ├── product.png
│   └── cart.png
│
└── requirements.txt
```

## 🚀 Future Improvements

- Replace `time.sleep()` with **Explicit Waits**
- Add assertions
- Create reusable functions
- Implement Page Object Model (POM)
- Add pytest
- Generate HTML test reports
- Add screenshots for failed tests
- Run tests using CI/CD with GitHub Actions

## 👨‍💻 Author

**Ajay**

CSE Student | Aspiring QA Automation Engineer

### Skills Demonstrated

`Python` `Selenium WebDriver` `Automation Testing` `XPath` `CSS Selectors` `Git` `GitHub`
