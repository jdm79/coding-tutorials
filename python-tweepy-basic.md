## How to make a basic Twitter bot with Python Tweepy


Create the Twitter account that you want to tweet from. Use an email to verify it, as well as a phone number (phone numbers can be used for multiple accounts). You’ll need an email-verified Twitter account in order to get your Twitter developer account.

Once you’ve created your Twitter account, go [here](https://developer.twitter.com/en/apply-for-access) to apply for a Twitter developer account.
 
choose Bot from the various choices
fill in the forms saying you just intend to use the tweet functionality, nothing more
you don’t want to use the data (although if you really do, you can change this later), but this will help move things along
keep the description brief and simple, and your application should be accepted quickly
wait for up to three days (could be a few hours though) for your application to be accepted

They don’t always tell you they’ve give you the green light, so check regularly on the developer account. If you are able to click ‘create an app’, you’re good to go.

When they’ve accepted your application, give your app a name on the developer account (best to keep it similar or the same to your new Twitter handle) and write the brief descriptions of what your bot will be up to.

### The code

``` Python

  from quotesFile import quotes as q
  import tweepy
  import random

  ### Twitter Bot oauth stuff
  consumer_key = ""
  consumer_secret = ""
  access_token = ""
  access_token_secret = ""
  auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
  auth.set_access_token(access_token, access_token_secret)
  api = tweepy.API(auth)



  def scraper():

    api.update_status(random.choice(q))

  scraper()

```

I’ve made an easy template I use for Twitter bots that are simply tweeting from text files in the same folder. When you’re web scraping and then cleaning data, before tweeting, we need a bit more code. 

### Imports:

``` Python
from quotesFile import quotes as q
import tweepy
import random

```

The top import is the name of the other file which contains a Python list of strings. In this case, the strings are our quotes or excerpts from text which will be tweeted. We’re imported the list, which is called quotesList and we’re going to refer to it as q in this file, because it’s less typing.

Tweepy is the Python Twitter library that makes everything nice and easy for us - and takes care of authentication with some Oauth stuff (which is usually a nightmare to do). The final import is Random, again from the Python library, which will allow us to choose a string from our list at random each time the function is run: random.choice(q) 

### Oauth:

``` Python
consumer_key = ""
consumer_secret = ""
access_token = ""
access_token_secret = ""
auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
auth.set_access_token(access_token, access_token_secret)
api = tweepy.API(auth)

```

### Put the Tweepy method in a function

``` Python
def scraper():

  api.update_status(random.choice(q))

scraper()

```
