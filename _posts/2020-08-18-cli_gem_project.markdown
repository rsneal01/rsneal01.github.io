---
layout: post
title:      "CLI Gem Project"
date:       2020-08-18 17:54:17 +0000
permalink:  cli_gem_project
---


As a fan of binge-worth TV series', I spend a lot of time checking out websites that rate TV shows, looking at critic scores and other info.  For my project, I decided to create a gem that would simplify the process of getting information about TV show reviews.  The pain point for the user is that one such rating site, IMDB.com, has a list of 250 shows, with their associated descriptions on an attached url.  I decided my app could simplify the interface of viewing these reviews by collecting data, including the descriptions from another webpage, and then listing this data for the top 5 shows (instead of 250), all in one location.

The first step in my process of creating this gem was to set up my bin file which I would be executing.  I decided to create a line of code in my bin file that created a new instance of the CLI class, and then called a method 'call' on that new instance.  In this manner, I could leave my bin file clean and simply, and then program all of the code for my CLI into a CLI class file in my lib folder.  When my program would be executed, the line of code in my bin file would then set off a series of methods that should run through all my necessary code.  

The next step was to try and "write the code you wish you had" as Avi puts it.  I wrote a call method, and a few methods that would be triggered when call was called.  These methods would essentially greet the user and present them with a list of shows.  This list of shows would be retrieved from a scraper class in a separate file, which I will talk about in a minute.  The user would be prompted to select a show by number, and a CLI method would use a conditional statement to return the approriate response based off the user input.  This conditional statement would be set up inside an until loop, such that my CLI would continuously prompt the user for input until they had typed exit.  Upon typing exit, my conditional statement would break, and the call method would hit a goodbye method that would print "Goodbye" to the user.  

Now I will talk through the scraper class, which gets triggered when the CLI hits it's list_shows method.  The list show method calls TopShows::Shows.all, which tells our program to go look in the scraper class all method for instructions.  Here, in the all method, I would call my two methods that I use to get the data from IMDB.  I played around with Replit for a while, using Nokogiri to open and select different elements that I had inspected from IMDB.  Eventually, I narrowed down my selectors and found the precise elements from IMDB that I wanted.  I then used an each statement to iterate over those elements, calling .first(5) in that method to make sure I didn't iterate over the entire 250 shows, but rather only the top 5.  I called .new in my each statement to basically say "go through the HTML data for the top 5 shows, and for each one, create a new show object.  Because my initialize method was set up to accept arguments for show attributes, I was able to plug in arugments for my .new call, and in one concise bit of code I was able to iterate over the show data and create 5 new show objects with attributes of title, score, and URL.  This method then returned the new show objects I created as an array.

I challenged myself to take my scraping a step further by trying to select and set the show description attribute.  The problem, which intimidated me at first, was that the description text was located on a separate URL which was attached to each show's link.  With some trial and error, I managed to set up a second scraping method, which accepted an argument of an array of show objects.  I theorized that if I could iterate over the show object array I had created in my first scraper method, and for each iteration plug in that individual show's URL attribute into Nokogiri's open URL argument, then I would be able to go in and select the text I wanted for each show's description.  I was pretty excited and surprised when my theory turned out to be correct.  My second scraper was correctly iterating and opening URL's, and then setting the selected text equal to the description attribute.  

Finally, I called my scraper methods in my TopShows::Shows.all method, so that my CLI would have access to the scraped data which it required in order to list show data.

All in all, I was pretty pleased and encouraged by my work on this project.  I was greatly intimidated at the start, and filled with self-doubt.  I was especially happy with my ability to slowly but surely work through the scraping methods and understand how to use iteration to write clean and simple scraping code.




