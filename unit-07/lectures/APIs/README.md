#DAY-07 APIs

_A full lecture is available [here](LECTURE.md)_

###Objective
**Students will be able to integrate an API into their project to provide additional functionality***

###Motivation
![Web APIs](https://s3.amazonaws.com/after-school-assets/API.png)
Think about how many cool apps there are out there: Instagram, Yelp, Yumly, Foursquare, Spotify (etc). There are a million; too many to list. All of these apps have a way for you to sign up and interact with the application. With Instagram, you can upload photos, search hashtags, and look at all the photos tagged in a specific location. 

In the same way that you can interact with an application, a program can as well. API stands for "Application Programming Interface". In a nutshell, an API is a set of instructions that allows developers to change and control existing web applications. It's a way for the developers of existing applications to allow other people to get their data in a controlled way. For example, the Facebook API has a specific function that allows developers to integrate posting to a Facebook wall. The Twitter API has a function that allows developers to display all of a user's tweets.

###Lesson Plan
+ We're going to use the Giphy API for this project. Let's create a file called `giphy.rb` in our development directory. 
+ We will be interacting with APIs through a Ruby wrapper; this is just a library of code written by Flatiron developers that lets us easily interact with Giphy. 
+ Because the code we're using to interact with the Giphy API lives in a separate file `giphy_wrapper.rb`, the first thing we have to do in our file `giphy.rb` is require the code: `require_relative 'giphy_wrapper.rb'`
+ The `giphy_wrapper.rb` file has a class `Giphy` defined, which has a whole bunch of functionality. Let's start by creating a new instance of the Giphy class.
  * When we run `ruby giphy.rb` in terminal, we should see the new instance of the Giphy class printed in terminal
  * So far we have not accessed the Giphy API, that's coming next
+ Let's start searching for funny images
  * The `search` method takes an a string as an argument.
  * We can save images in our file and run it, and we should see a huge output of URLs like this:

+ Giphy.com has search functionality. The URL for the programatic call `giph.search`... hits this URL on giphy.com
```
http://api.giphy.com/v1/gifs/search?q=funny+cat+orange&api_key=dc6zaTOxFJmzC
```

+ Let's break this down into parts. First you have the base URL for the search endpoint (noticed `search` in the URL):

  * Followed by a `?` which indicates - Hey! Some custom parameters are coming up. 
  * The first parameter is a query (q for query) for gifs tagged
  * Followed by a `&` which indicates - Hey! Another URL parameter is coming at you.
    * This is an API key provided by Giphy. Every request you make must have this api key on the end of it, like a key unlocking the API.

+  Copy and paste the url into your browser to see the JSON response that Giphy is going to send back to you.
  * JSON is a "data-interchange format" which is basically a neat way to look at the responses from an APIs
  * This thing probably looks intimidating, but it's essentially a nested hash. Let's call this hash object `response`. 
  * If we want to pull the `data` array out of this hash that would be `response["data"]`
  * Drill down deeper to the first item in that array: `response["data"][0]`. 

We have a huge module on APIs and walkthroughs of good APIs for you all to practice integrating APIs into your projects!

###Resources
[Here's a great Quora page on APIs for laypeople.](http://www.quora.com/In-laymans-terms-what-is-an-API-1)

[And here's an excellent explanation of API's from How Stuff Works](http://money.howstuffworks.com/business-communications/how-to-leverage-an-api-for-conferencing1.htm)