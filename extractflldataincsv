
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
import time
from selenium.webdriver.common.by import By
from selenium.webdriver.support.wait import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
import pandas as pd

driver=webdriver.Chrome()

driver.get("https://www.nytimes.com/international/section/politics")

titles=driver.find_elements(By.XPATH,"//*[@id='stream-panel']/div/ol/li/div/div/a/h2")
summarys=driver.find_elements(By.XPATH,"//*[@id='stream-panel']/div/ol/li/div/div/a/p")
authors=driver.find_elements(By.XPATH,"//*[@id='stream-panel']/div/ol/li/div/div/a/div/p")
images=driver.find_elements(By.XPATH,"//*[@id='stream-panel']/div/ol/li/div/div/a/div/figure/div/img")
dates=driver.find_elements(By.XPATH,"//*[@id='stream-panel']/div/ol/li/div/div/span")
Title=[]
Summary=[]
Author=[]
Image=[]
Date=[]
for i in range(len(titles)):
    Title.append(titles[i].text)
    Summary.append(summarys[i].text)
    Author.append(authors[i].text)
    Image.append(images[i].get_attribute("src"))
    Date.append(dates[i].text)
driver.quit()

df=pd.DataFrame({'Title':Title,'Descriptions':Summary,'Author':Author,'Image':Image,'Date':Date})
df.to_csv('data.csv',index=False)
print(df)
