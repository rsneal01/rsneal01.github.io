---
layout: post
title:      "Sinatra Portfolio Project - Video Game Manager"
date:       2021-04-11 17:29:06 +0000
permalink:  sinatra_portfolio_project_-_video_game_manager
---


While the whole model-view-controller system definitely took me a while to wrap my head around, with enough practice and repetition the flow of actions started to make sense finally.  I decided to create a simple content management system based around video games, such as the way an app like Steam does.  

I drew up a file structure and created migrations similar to what I had done in previous labs.  Once I got into the controllers, I started to become challenged to be flexible with my code.  I ran into some issues with my code that were different from issues that would arise from, for example, an app like Fwitter.  This is where some of the fun started for me, because it made me think creatively, and I was surprised at my own ability to shape my code around what I wanted the user experience to look like. 

For example, on Fwitter, we had a delete action that allowed a user to delete a tweet that they had created.  This delete action worked by finding the tweet object in question, and calling .delete on it, effectively removing the tweet from that specific user's tweets AND the tweet index page for all users.  This made sense for Fwitter, where the user is the creator of their content.  In my app, on the other hand, this functionality didn't make sense, I came to realize.  Playing around in my brower, I discovered that when a user would try and remove a game from their library, it was deleting the game object from the entire games library, and no longer displaying on my games index page.  This didn't make sense from a practical perspective, because if one user deletes a game, it shouldn't remove the game from all users.

So as I thought about it, I realized that rather than deleting the game object in question, I wanted to access the current user's ARRAY of a games, and then remove this game from their array only.  With a little googling, I discovered that you can call .delete(value) on an array, plugging in the value of the element you want to delete.  I ended up writing:

@user.games.delete(@game)

and successfully removed a game from my user's library, while maintaining the game in the general Games index.

I had a few other obstacles like this arise, during which I was challenged to think outside the box of what I had done in previous labs.  I was encouraged to see my ability to be flexible and apply what Flatiron has taught me thus far in a creative way. 
