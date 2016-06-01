# Web-scraping-using-BeautifulSoup
# Data Format
# <tr><td>Modu</td><td><span class="comments">90</span></td></tr>
# <tr><td>Kenzie</td><td><span class="comments">88</span></td></tr>
# <tr><td>Hubert</td><td><span class="comments">87</span></td></tr>

import urllib
from Beautifuls import BeautifulSoup # import bs library
numbers = list()
url = raw_input('Enter - ')
html = urllib.urlopen(url).read() 
soup = BeautifulSoup(html) # scraping
tags = soup('span') # a list of <span> tag
for tag in tags:
	numbers.append(int(tag.string)) # extract numbers from each line

print 'Sum', sum(numbers)
	
