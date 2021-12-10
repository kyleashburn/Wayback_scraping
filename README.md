# Wayback_scraping
The goal of this project was to automate the process of collecting captures from the wayback machine for research. A friend of mine was doing this manually and I felt there had to be a better way. Luckily, turns out there's an api that is quite helpful: https://github.com/internetarchive/wayback/tree/master/wayback-cdx-server.

Using that API and the requests library in Python, I was able to a) find the resources that had been captured and b) follow up by using the pdfkit library to make pdf downloads of those pages. 
