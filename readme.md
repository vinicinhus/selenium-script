# Selenium Webdriver Utilities

This Python script provides a set of utility functions using the Selenium WebDriver library for automating web 
interactions. The functions are designed to interact with visible elements on a web page, handling actions such as 
keyboard input, clicking, clearing text input, selecting options from dropdowns, and switching between iframes.

## Functions

### visible_keys
```python
def visible_keys(driver: webdriver, locator_strategy: By, locator: str, keys: str) -> None:
```
This function performs keyboard input on a visible element identified by a locator. 
It waits for the element to become visible on the web page and then sends the specified keys to it.

### visible_click
```python
def visible_click(driver: webdriver, locator_strategy: By, locator: str) -> None:
```
This function performs a click action on a visible element identified by a locator. It waits for the element to become 
clickable on the web page and then clicks it.

### visible_clear
```python
def visible_clear(driver: webdriver, locator_strategy: By, locator: str) -> None:
```
Clears the text input of a visible element identified by a locator. It waits for the element to become visible on the 
web page and then clears any text input in it.

### select_option_by_value
```python
def select_option_by_value(driver: webdriver, locator_strategy: By, locator: str, option_value: str):
```
Selects an option from a dropdown by its value. It waits for the dropdown element to be present on the web page and 
then selects the specified option value.

### switch_to_iframe
```python
def switch_to_iframe(driver: webdriver, locator_strategy: By, locator: str) -> None:
```
Switches the driver's context to an iframe identified by a locator. It waits for the iframe to be present on the web 
page before switching.

### switch_to_default_content
```python
def switch_to_default_content(driver: webdriver) -> None:
```
Switches the driver's context back to the default content. This function is useful when working within an iframe 
or another context.

### is_element_present
```python
def is_element_present(driver: webdriver, locator_strategy: By, locator: str) -> bool:
```
Checks if an element identified by a locator is present on the web page. Returns True if the element is found, False otherwise.

## Usage

1. Import the necessary modules:
```python
from selenium import webdriver
from selenium.common.exceptions import NoSuchElementException
from selenium.webdriver.common.by import By
from selenium.webdriver.support import expected_conditions as ec
from selenium.webdriver.support.ui import WebDriverWait, Select
```

2. Copy and use the functions in your Selenium WebDriver automation script.
```python
# Example usage
driver = webdriver.Chrome()

# Perform visible click
visible_click(driver, By.ID, "my_button_id")

# Input text into a visible element
visible_keys(driver, By.NAME, "username", "my_username")

# Check if an element is present
if is_element_present(driver, By.XPATH, "//div[@class='my_class']"):
    print("Element is present!")

# Close the browser window
driver.quit()
```

Feel free to customize and integrate these functions into your Selenium automation projects for efficient and reliable web interactions.
