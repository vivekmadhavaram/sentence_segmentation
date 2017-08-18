# sentence_segmentation
import requests
import re
from bs4 import BeautifulSoup

r = requests.get("https://en.wikipedia.org/wiki/Hello_(Adele_song)")
soup = BeautifulSoup(r.content,"html.parser")
line1=''
for line in soup.findAll('p'):
    line1=line1+line.getText()
line1=re.sub("[\[0-9?\]]",'',line1)
line2=line1.split(". ")
for l in line2:
    print(l)
    print('\n')
