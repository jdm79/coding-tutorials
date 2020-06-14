### How to make a basic Twitter bot with Python Tweepy


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