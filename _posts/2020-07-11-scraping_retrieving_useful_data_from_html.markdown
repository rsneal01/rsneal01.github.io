---
layout: post
title:      "Scraping:  Retrieving Useful Data from HTML"
date:       2020-07-11 16:39:29 +0000
permalink:  scraping_retrieving_useful_data_from_html
---


Scraping is the process of parsing through a webg pages HTML and selecting specific, useful data.  While it would be easier to use an API, sometimes there is data we might need which is not available through an API.  In this case, using specific code to "scrape" a page can be helpful.

A gem called Nokogiri is useful for breaking down a pages HTML into many small pieces, which allows for easier precision in our coding.  From here, we can use a browser's element inspector to scan over the data that we are interested in.  Once we locate an object we want data from, we can look at the line of code y hovering over the object with our inspecter tool.  This allows us to see the line of code, and where it is nested in the HTML, so that we can apply a CSS selector to grab it.  We practiced using selectors to move through several layers of nested code.  It seems like a process that can get pretty tricky and complicated as one moves through deeper levels of nested code.  Being very precise, I would presume, is important in mastering scraping.

Sometimes a web page may have its HTML updated, and our scraping code may fail.  In this instance, we would have to go back and reprogram our scraping code.  However, updating some a scraper can often be more time-efficient than manually updating data.


