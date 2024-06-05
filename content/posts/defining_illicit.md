---
title: How we built Groupint to identify who's talking to whom on Telegram
draft: false
---

In recent years, Telegram has become popular for threat actors to engage in illicit activity. These actors range from simple fraudsters to cybercriminals and Russian military and intelligence personnel. 

Telegram is popular because of its end-to-end encrypted messaging, yet, the platform is not as anonymous as users believe. In fact, it's a rich repository of information.

Groupint is a recent OSINT tool that enables investigators to identify networks on Telegram. I helped develop this tool as part of the R&D team at OSINT for Ukraine and in this post, we'll explore how we built an app that lets users see who's talking to whom on Telegram.

## What is Groupint?

Groupint is an app that enables investigators to scrape data from Telegram groups and connect users through an intuitive and visually appealing graph and user interface. 

This app is an open-source tool developed by OSINT for Ukraine, an independent non-profit foundation dedicated to using open-source intellgience to investigate war crimes in relation to the Russo-Ukrainian War.

Groupint enables investigators to analyse networks within specific Telegram communities by scraping users and connecting who's who in a graph database. 

To identify all the users and who they're talking to, simply input the name of a group that you're interested in and the app extracts all of the users and the groups that they are part of.

Groupint enables network analysis and opens up a host of opportunities. Investigators can identify threat actors and their networks. They can also map trends in how illicit finance and threat actors interact with social media.

You might wonder how it is possible to scrape and connect users between groups in an end-to-end encrypted app that supposedly provides you with unprecedented anonymity.

The answer is simple; Telegram data is routinely sold in Russia. 

## Telesint

Groupint is powered by [Telesint](https://telesint.dev/en/), a database of over 3 million open Telegram chats and tens of thousands of private chats. Their bot is designed to search for people in open and closed Telegram groups. 

Though Telesint doesn't collect "personal data", the bot collects enough data points to link users from different groups. 


`id` - user's unique id 

`label`- user's alias 

`group` - a list of Telegram groups that user is a member of


{{% details title="Click me to reveal example of user data" closed="true" %}}
```json

{
    "data": {
      "id": 94252564,
      "label": "andrey600",
      "username": "andrey600",
      "group": [
        "chat_massovka",
        "silovikigroup",
        "mesles",
        "komsomolka_ru"
      ]
    }
  },


```
{{% / details %}}


## Telethon





