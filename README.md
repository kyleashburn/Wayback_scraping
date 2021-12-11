# Wayback_scraping
## Background:
The goal of this project was to automate the process of collecting captures from the wayback machine for research. A friend of mine was doing this manually and I felt there had to be a better way. Luckily, turns out there's an api that is quite helpful: https://github.com/internetarchive/wayback/tree/master/wayback-cdx-server.

Using that API and the requests library in Python, I was able to a) find the resources that had been captured and b) follow up by using the pdfkit library to make pdf downloads of those pages. 

## Methodology:
1. Retrieve a filtered and collapsed json result set of stored urls from the CDX server
2. Remove duplicates from that set of stored urls
3. Download the resources at those urls
  * Check if PDF, DOC, or HTM
  * pdfkit for HTM, requests for PDF and DOC 

## Assumptions:
I made the following assumptions:
* I made the assumption that we only cared about things where the CDX server returned a 200 status code (they exist/are responsive). 
* I made the assumption that we wanted to collapse duplicates together (relying on the filtering in the API to a good extent).
* I made the assumption that when choosing between more results than the Wayback machine has and less results, that more is better. 

## Challenges:
There were a number of challenges associated with this little project:
* The CDX server API wasn't quite as clearly documented as I'd like
* The results for the CDX server were different than the results found on the Wayback Machine itself

## Lessons Learned:
* Just try things
  * Trying things out didn't break things too much
* Requests is a very powerful library
* The internet is truly epehmeral
* JSON doesn't always mean JSON
  * the JSON results from the CDX are actually lists. Friendlier to work with though

## Results:
* Returns a set of around 420 scrapped urls
  * mostly filtered and reduced for relevance
* Saves a decent chunk of effort for my friend
