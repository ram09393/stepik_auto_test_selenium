import math

def calc(x):
  return str(math.log(abs(12*math.sin(int(x)))))

from selenium import webdriver
from selenium.webdriver.common.by import By
import time

browser = webdriver.Chrome()
link = "http://suninjuly.github.io/alert_accept.html"
browser.get(link)
button2 = browser.find_element(By.CLASS_NAME, "btn")
button2.click()
confirm = browser.switch_to.alert
confirm.accept()

x_element = browser.find_element(By.ID, "input_value")
x = x_element.text
y = calc(x)

browser.switch_to.window(browser.window_handles[0])

input1 = browser.find_element(By.ID,'answer')
input1.send_keys(x)

button2 = browser.find_element(By.CLASS_NAME, "btn")
button2.click()

time.sleep(30)
browser.quit()

