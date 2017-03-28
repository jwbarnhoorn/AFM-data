
from bs4 import BeautifulSoup
from urllib.request import urlopen, urlretrieve

url = 'https://www.afm.nl/nl/professionals/registers/alle-huidige-registers.aspx?type={1331D46F-3FB6-4A36-B903-9584972675AF}'
u = urlopen(url)

try:
    html = u.read().decode('utf-8')
finally:
    u.close()

soup = BeautifulSoup(html, "html.parser")

# Select .csv 
for link in soup.find_all(attrs={'class': 'download_file'}):
    if href.endswitch('.csv'):
        print link.get('href')
