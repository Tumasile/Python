#import selenium libraries to python
from selenium import webdriver

import pyautogui

#import time for delay
from time import sleep
from datetime import datetime
start_time = datetime.now()

download_dir = "C:\\Users\\tchilunga\\Documents\\PythonProjects\\webProcess\\zipFiles\\"
#def __get_chrome_driver(self, download_dir):
chrome_options = webdriver.ChromeOptions()

prefs = {"download.default_directory": download_dir}
chrome_options.add_experimental_option("prefs", prefs)

driver = webdriver.Chrome(executable_path="C:\\Users\\tchilunga\\AppData\\Local\\Programs\\Python\\Python36-32\\drivers\\chromedr\\chromedriver.exe", chrome_options=chrome_options)

driver.maximize_window()

#open and get the link
driver.get('https://github.com/login?return_to=%2Fcaetanus%2Fwindows-file-changes-notify%2Ftree%2Fmaster%2Fwinwatcher')

#delay
sleep(1)
#find element on the html page by inspect element
textArea = driver.find_element_by_id('login_field')

# type to the field
textArea.send_keys('username')

#find element on the html page by inspect element
textArea = driver.find_element_by_id('password')

# type to the field
textArea.send_keys(password)


# find the button. inspect element, copy xpath from webpage
submit_button = driver.find_elements_by_xpath('//*[@id="login"]/form/div[4]/input[3]')[0]
# click submit button
submit_button.click()

sleep(1)
#click menu
submit_button4 = driver.find_elements_by_xpath('//*[@id="user-links"]/li[3]/details/summary')[0]
# click submit button
submit_button4.click()

sleep(1)
#profile
clickProfile = driver.find_elements_by_xpath('//*[@id="user-links"]/li[3]/details/ul/li[3]/a')[0]
clickProfile.click()

sleep(1)
#click hello
clickHello = driver.find_elements_by_xpath('//*[@id="js-pjax-container"]/div/div[2]/div[4]/div[1]/div[1]/ol/li[4]/span/span/a/span')[0]
clickHello.click()

sleep(1)
#download Icon
downloadIcn = driver.find_elements_by_xpath('//*[@id="js-repo-pjax-container"]/div[2]/div[1]/div[4]/details/summary')[0]
downloadIcn.click()

sleep(1)
#click download
downloadBtn = driver.find_elements_by_xpath('//*[@id="js-repo-pjax-container"]/div[2]/div[1]/div[4]/details/div/div/div[3]/a[2]')[0]
downloadBtn.click()

#move mouse... uncomment if headless is commented out
#pyautogui.click(1650, 190, duration=0.95)

sleep(1)
#click menu
submit_button5 = driver.find_elements_by_xpath('//*[@id="user-links"]/li[3]/details/summary/img')[0]
# click submit button
submit_button5.click()

sleep(2)
#logout
logoutBtn = driver.find_elements_by_xpath('//*[@id="user-links"]/li[3]/details/ul/li[9]/form/button')[0]
# click submit button
logoutBtn.click()

#close connection
driver.close()
sleep(2)
print(' \n Logged Out from StackOverFlow')

print(' \n Chrome Window Closed')

end_time = datetime.now()
print('\n Duration of the full process: {}'.format(end_time - start_time))
