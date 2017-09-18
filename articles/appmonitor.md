---
layout: article
title: Monitoring Google Play for App/APK Version Changes
permalink: /appmonitor/
comments: true
published: true
---
If you ever need to automatically monitor whether an app in *Google Play* has been updated. I have had cases in the past where we wanted to know when our Customer's/Partner's apps were updated as soon as possible. Here is a simple Python script that helps with this automation.

You will need to run this script in CRON (recommended) or in a loop to check periodically.

Need the following packages (Python 3):

```
pip3 install requests
pip3 install bs4
pip3 install tweepy

```

## Imports
```
import requests
from bs4 import BeautifulSoup
import re
import tweepy
import time
```

## Twitter Access Stuff - Since this example is using direct message as an example

```

## Twitter Access Stuff- Set this up at developer.twitter.com
consumer_key="COPY_YOURS_HERE"
consumer_secret = "COPY_YOURS_HERE"
access_token = "COPY_YOURS_HERE"
access_token_secret = "COPY_YOURS_HERE"
```

## Check the version in the store
By screen scraping of the Google Play Store using the Beautiful Soup package

```
def checkVersionInStore(packageName):
    # Act like a regular browser
    headers = {'User-Agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_10_1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/39.0.2171.95 Safari/537.36'}

    # load the page from Google Play
    page = requests.get("https://play.google.com/store/apps/details?id="+packageName, headers=headers)

    soup = BeautifulSoup(page.content, 'html.parser')

    version = soup.find_all("div", {"itemprop" : "softwareVersion"})

    # Need to add more defensive code here. Omitted for simplicity
    versionText=str(version[0].text)

    return versionText
```

## Create a mechanism to send a notification
For e.g. Tweet a direct message to a set of users about the change in version

```
# Way to Communicate to users via a Direct Message in Twitter
def sendTweet(twitterIds, message):
    # Authenticate to Twitter
    auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
    auth.set_access_token(access_token, access_token_secret)
    api = tweepy.API(auth)

    # Sending Message via Tweet
    print("Sending Message via Tweet - " + message)

    # Send Tweet
    for tid in twitterIds:
        api.send_direct_message(user=tid, text=message)
```

## Put it together
```
def checkForAppChange(packageName, expectedVersion, expectedVersionFoundList, newVersionFoundList):

    versionText = checkVersionInStore(packageName)

    # if the Verson found is the same or different, send the notification
    if (versionText.find(expectedVersion) != -1):
        sendTweet(expectedVersionFoundList, "Version has not changed:" + versionText)
    else:
        sendTweet(newVersionFoundList, "****VERSION IS CHANGED****:" + versionText)
```

## Finally make the call for your apps


```
# Main
print("Checking App Version Change:" + time.asctime( time.localtime(time.time())))

# Using paypal app as a sample
checkForAppChange(packageName="com.paypal.android.p2pmobile",
                  expectedVersion="6.14.1",
                  expectedVersionFoundList=["twitter_id_1"],
                  newVersionFoundList=["twitter_id_1", "twitter_id_2"])

```

It is all put together in the following [Gyst](https://gist.github.com/rrama08/00cde3ae94de71330d3ad95ef8859cdd)
