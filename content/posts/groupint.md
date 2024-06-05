---
title: Unmask networks on Telegram with Groupint
draft: false
---

![graph](/images/groupintgraph.png "Graph of networks on Telegram")


In recent years, Telegram has become popular for threat actors to engage in illicit activity. These actors range from simple fraudsters to cybercriminals and Russian military and intelligence personnel. 

Telegram is popular because of its end-to-end encrypted messaging, yet, the platform is not as anonymous as users believe. In fact, it's a rich repository of information.

Investigators can use this information to identify networks on Telegram and connect who's talking to whom.

Groupint is a recent OSINT tool investigators can use to invesigate networks on Telegram. I helped develop this tool as part of the R&D team at OSINT for Ukraine and in this post, we'll explore how we built an app that lets users see who's talking to whom on Telegram.

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


## Architecture

The architecture behind Groupint is straightforward. Our user logs in to Groupint, our streamlit app. The group that the user queries is communicated to Telesint using a python library called [Telethon](https://docs.telethon.dev/en/stable/). This library is crucial. We use it to connect to Telesint and scrape results. 

![architecture](/images/architecture_groupint.png "Groupint Architecture")
 

Results are stored in a Neo4j database, which we use to draw connections between individuals in different groups in a graph that outlines each network present on Telegram.

![graph](/images/groupintgraph.png "Groupint Architecture")


## Get started


### Acquire API Credentials 

When you log in to Groupint, you  set up a session with Telesint to access data on Telegram groups. Creating a session requires that you provide the phone number linked to your Telegram account and your Telegram API id and API hash.

Acquire the API id and API hash from Telegram. You need to do the following:

1. Sign up to [Telegram](https://core.telegram.org/api/obtaining_api_id)
2. Log in to your Telegram account [](https://my.telegram.org).
3. Got to "API development tools" section and fill out the form.
4. You will get your API id and API hash parameters required for user authorization.
5. For the moment, each number can only have one api id connected to it.

### Prerequisites

Make sure that you have installed on your system:

1. Docker to compose the project
2. Python 3.11
3. Poetry to install python dependencies and set up your virtual environment

### Clone project and start containers

Clone the Groupint project from the OSINT for Ukraine Github accoun and run docker-compose or docker compose to set up the project .

```
git clone https://github.com/OSINT-for-Ukraine/groupint.git
cd groupint
docker-compose up

```

Set your login credentials. Create a secrets.toml file inside the streamlit folder and set your password.

```
# Create secrets file 
cd streamlit 
touch secrets.toml
# Set password variable
password = "xxxx"
```

### Run a local instance of Groupint

You can start your local instance of Groupint and run the app locally with the command:

```
streamlit run interface.py
```


