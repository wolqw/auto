```python
from selenium import webdriver
from webdriver_manager.chrome import ChromeDriverManager
from selenium.webdriver.chrome.options import Options
from selenium.webdriver.chrome.service import Service
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
import time

options = Options()
options.add_argument('--ignore-certificate-errors')
options.add_argument('--ignore-ssl-errors')
options.add_argument('--disable-blink-features=AutomationControlled')
options.add_argument("--user-agent=Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/116.0.0.0 Safari/537.36")

service = Service(ChromeDriverManager().install())
driver = webdriver.Chrome(service=service, options=options)
wait = WebDriverWait(driver, 10, poll_frequency=1)

driver.get("https://demoqa.com/alerts")

promtButton = ("xpath", "//button[@id='promtButton']")
wait.until(EC.element_to_be_clickable(promtButton)).click()
alert = wait.until(EC.alert_is_present())
driver.switch_to.alert
alert.send_keys("Abracadabra")
alert.accept()
time.sleep(3)


button_confirmButton = ("xpath", "//button[@id='confirmButton']")
wait.until(EC.element_to_be_clickable(button_confirmButton)).click()
alert = wait.until(EC.alert_is_present())
driver.switch_to.alert
print(alert.text)
alert.dismiss()
time.sleep(2)


button = ("xpath", "//button[@id='alertButton']")
wait.until(EC.element_to_be_clickable(button)).click()
alert = wait.until(EC.alert_is_present())
driver.switch_to.alert
alert.accept()
time.sleep(2)
