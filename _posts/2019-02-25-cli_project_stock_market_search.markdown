---
layout: post
title:      "**CLI Project: Stock Market Search**"
date:       2019-02-25 22:27:07 +0000
permalink:  cli_project_stock_market_search
---


In college I majored in Business Economics, so when I saw this project I knew I wanted it to have something to do with the stock market. Originally I had wanted to scrape my info from [Etrade's website](https://www.etrade.wallst.com/v1/stocks/snapshot/snapshot.asp?symbol=AAPL) - as it is my favorite site to find stock related information on. This site proved to be too difficult for me to scrape but more on that later. 

I started out by watching all the videos provided in the project instructions, which was the best thing I could have done for myself. I was then easily able to create my repo and start working on the details of my project. I had breifly written out what I wanted the system to do in my cli.rb file #call method so I can adjust as I go. After refactoring and making the file neater, I had a very basic cli set up that worked when I tested it. 

Time to start adding scraped data. I knew I needed a few things set up first so I required nokogiri, open-uri, and pry in my files. I created a Company class and a Scraper class. My Company class is responsible for taking a url, sending it to the Scraper class, and returning a new Company instance with attributes set from the scraped data. The Scraper class is responsible for taking that url and picking out the new company's name, overview, price, updated timestamp, and page url.

I started running the system and everything was working as it should except for the scraped data. I couldn't figure out why it wasn't working for the longest time. Using pry, I finally found the culprit: the website itself. Everything I was trying to scrape from Etrade was returning with an empty string, so when the user types ticker symbol AAPL, instead of getting the company name to be "Apple Inc." it just gets "". 

I decided to try out a different website called MarketWatch. Everything started working the way it should, name, price, etc. The only thing now that I had to fix was the overview, which was scraping not only the paragraph but blank spaces and a button that says "(view full profile)". I went to Google to find out how to only get the <p> (paragraph overview description) without it's child <span> ("(view full profile)"). I found if you code it like this ("p.description__text > text()") it gets rid of the view profile button.  Adding .strip to the end also got rid of the blank spaces. 

Everything is working now except of the fact that when you enter an invalid ticker symbol, it still lets you go through the menu options but you recieve no information on anything. This was easily fixed by adding a conditional where if the system can't find a company's name using the input, it returns a message saying that it couldn't be found please try again. 

Finally everything is up and running as it should be. The user is able to find out information like current market prices and company information by entering the stock's ticker symbol. You can find my finished project and code [here](https://github.com/alexmpalermo/stock_market_search).
