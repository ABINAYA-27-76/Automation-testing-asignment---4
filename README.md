# Automation-testing-assignment---4
## Coding
```
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
import time

# Open Chrome
driver = webdriver.Chrome()
driver.maximize_window()

wait = WebDriverWait(driver, 10)

url = "https://www.saucedemo.com/"



driver.get(url)

print("Website opened successfully")
print("Title:", driver.title)

time.sleep(1)



username = wait.until(
    EC.visibility_of_element_located(
        (By.ID, "user-name")
    )
)

username.send_keys("standard_user")

print("Username entered successfully")

time.sleep(1)



password = driver.find_element(
    By.ID,
    "password"
)

password.send_keys("secret_sauce")

print("Password entered successfully")

time.sleep(1)



login = wait.until(
    EC.element_to_be_clickable(
        (By.ID, "login-button")
    )
)

login.click()

print("Login successful")

time.sleep(2)

products = wait.until(
    EC.visibility_of_element_located(
        (By.CLASS_NAME, "title")
    )
)

print("Page:", products.text)

if products.text == "Products":
    print("TC05 PASSED")
else:
    print("TC05 FAILED")

time.sleep(1)



add_product = wait.until(
    EC.element_to_be_clickable(
        (By.ID, "add-to-cart-sauce-labs-backpack")
    )
)

add_product.click()

print("Product added successfully")

# Check cart
cart = driver.find_element(
    By.CLASS_NAME,
    "shopping_cart_badge"
)

print("Cart quantity:", cart.text)

time.sleep(1)



driver.find_element(
    By.CLASS_NAME,
    "shopping_cart_link"
).click()

print("Cart opened successfully")

time.sleep(2)

product = wait.until(
    EC.visibility_of_element_located(
        (By.CLASS_NAME, "inventory_item_name")
    )
)

print("Product in cart:", product.text)

time.sleep(1)


wait.until(
    EC.element_to_be_clickable(
        (By.ID, "checkout")
    )
).click()

print("Checkout page opened")

time.sleep(1)

# First name
driver.find_element(
    By.ID,
    "first-name"
).send_keys("Abhi")

# Last name
driver.find_element(
    By.ID,
    "last-name"
).send_keys("Test")

# Postal code
driver.find_element(
    By.ID,
    "postal-code"
).send_keys("600001")

print("Customer details entered")

time.sleep(1)



wait.until(
    EC.element_to_be_clickable(
        (By.ID, "continue")
    )
).click()

print("Order summary opened")

time.sleep(1)

wait.until(
    EC.element_to_be_clickable(
        (By.ID, "finish")
    )
).click()

print("Order placed successfully")

# Check confirmation
confirmation = wait.until(
    EC.visibility_of_element_located(
        (By.CLASS_NAME, "complete-header")
    )
)

print("Confirmation:", confirmation.text)

time.sleep(2)

# Back to products
driver.find_element(
    By.ID,
    "back-to-products"
).click()

time.sleep(1)

# Open menu
wait.until(
    EC.element_to_be_clickable(
        (By.ID, "react-burger-menu-btn")
    )
).click()

time.sleep(1)

# Logout
wait.until(
    EC.element_to_be_clickable(
        (By.ID, "logout_sidebar_link")
    )
).click()

print("Logout successful")

time.sleep(2)

driver.quit()


```


<img width="1782" height="990" alt="Screenshot 2026-10-07 133959" src="https://github.com/user-attachments/assets/7f3c567b-0f49-4607-a0d2-fbbc4fe4214a" />
<img width="1557" height="851" alt="Screenshot 2026-10-07 133908" src="https://github.com/user-attachments/assets/58f0b2e1-acbf-4bfe-ace1-95955369d4ee" />
<img width="1380" height="993" alt="Screenshot 2026-10-07 133538" src="https://github.com/user-attachments/assets/6b188c51-41aa-499b-8f23-e1ae350c678e" />
<img width="1595" height="1015" alt="Screenshot 2026-10-07 133858" src="https://github.com/user-attachments/assets/b16ee1f2-42b4-4662-a58a-bec53058a6a4" />


# Alter ,wait ,dropdown button
```
from selenium import webdriver
from selenium.webdriver.common.by import By
import time

# Open Chrome
driver = webdriver.Chrome()

# Open website
driver.get("https://demo.automationtesting.in/Alerts.html")

# Maximize browser
driver.maximize_window()

# Click Alert with OK button
driver.find_element(By.XPATH, "//button[contains(text(),'click the button to display an alert box')]").click()

# Switch to alert
alert = driver.switch_to.alert

# Print alert message
print("Alert Message:", alert.text)

# Click OK
alert.accept()

print("OK button clicked successfully")

time.sleep(3)

# Close browser
driver.quit()
```
```
from selenium import webdriver
from selenium.webdriver.common.by import By
import time

# Open Chrome
driver = webdriver.Chrome()

# Open website
driver.get("https://demo.automationtesting.in/Alerts.html")

# Maximize browser
driver.maximize_window()

# Click Alert with OK & Cancel
driver.find_element(By.XPATH, "//button[contains(text(),'display a confirm box')]").click()

# Switch to alert
alert = driver.switch_to.alert

# Print alert message
print("Alert Message:", alert.text)

# Click Cancel
alert.dismiss()

print("Cancel button clicked successfully")

time.sleep(3)

# Close browser
driver.quit()
```
```
from selenium import webdriver
from selenium.webdriver.common.by import By
import time

# Open Chrome
driver = webdriver.Chrome()

# Open website
driver.get("https://demo.automationtesting.in/Alerts.html")

# Maximize browser
driver.maximize_window()

# Click Alert with Textbox
driver.find_element(By.XPATH, "//button[contains(text(),'demonstrate the prompt box')]").click()

# Switch to alert
alert = driver.switch_to.alert

# Print alert message
print("Alert Message:", alert.text)

# Enter name in textbox
alert.send_keys("Abinaya")

# Click OK
alert.accept()

print("Name entered and submitted successfully")

time.sleep(3)

# Close browser
driver.quit()
```







<img width="1541" height="950" alt="image" src="https://github.com/user-attachments/assets/95f85a4a-663b-4bec-8b83-b9214b19d14d" />
<img width="1292" height="982" alt="image" src="https://github.com/user-attachments/assets/c7428347-1360-4703-bf32-8651f10d1a84" />

## Enter Name

```
from selenium import webdriver
from selenium.webdriver.common.by import By
import time

driver = webdriver.Chrome()

driver.get("https://the-internet.herokuapp.com/javascript_alerts")
driver.maximize_window()

# Click prompt button
driver.find_element(
    By.XPATH,
    "//button[text()='Click for JS Prompt']"
).click()

# Switch to alert
alert = driver.switch_to.alert

# Print prompt message
print("Prompt Message:", alert.text)

# Enter name
alert.send_keys("Abinaya")

# Click OK
alert.accept()

print("Name entered successfully")

time.sleep(3)

driver.quit()

```
<img width="1361" height="895" alt="image" src="https://github.com/user-attachments/assets/75f9697f-f88b-4ff7-82d3-93273490545b" />

