```python
from selenium import webdriver
from webdriver_manager.chrome import ChromeDriverManager
from selenium.webdriver.chrome.service import Service
import time

service = Service(executable_path=ChromeDriverManager().install())
driver = webdriver.Chrome(service=service)

driver.get("https://hyperskill.org/tracks")

driver.find_element("xpath", "//ul/li").click()

driver.get("https://hyperskill.org/tracks")

driver.find_element("xpath", "(//a)[11]").click()

driver.find_element("xpath", "(//a)[15]").click()

driver.find_element("xpath", "(//div[@class='mb-4 filtered-item col-md-6 col-12'])[3]").click()

driver.back()

driver.find_element("xpath", "(//button[contains(text(), 'Sign in')])").click()

