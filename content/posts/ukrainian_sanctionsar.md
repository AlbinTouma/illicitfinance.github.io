---
title: Four steps to make any sanctions investigation successful
date: 2024-04-19
draft: false
---

We often talk about sanctions in the context of efficiency or individual cases. Who's who in the sanctions space has, as a result, become elusive when there are characteristics, data sets, and methods of revealing sanctioned entities and their networks. 

Lets explore four common steps in the research process behind investigations into sanctions, from the the design of research methods to the collection and analysis of information.


{{% steps %}}

### Research Design

#### Ontology

The firt step in researching who's who in the sanctioned space is knowing how to describe entities and relations beetween them. In industry, we describe our domain and its objects in an [ontology](https://en.wikipedia.org/wiki/Ontology). 

An ontology is a formal naming and definition of categories, properties, and relations betweeen concepts, data, or entities.

I recommend using the Follow the Money ontology.

**Follow the Money**

Follow the Money is an ontology that is commonly used in anti-corruption investigations. 

Their ontology defines entities revelant in such investigations, like people or companies, and helps investigators create a graph of relationships. 

One of the most common tasks for an investigative reporter is to work out if one thing is the same as another. Is the person who owns a sanctioned company the same guy who is a mayor in my city?

Many facts might provide hints that allow us to establish if he is "our guy". Do the individuals have the same name, date of birth, nationality, passport number? Do we know about links to other individuals or companies in both data sets? 

When you have a clearly defined ontology, you can turn representations of objects and events into complex data and compile and cross-reference these hints.

The Follow the Money ontology consists of schemata ie object types that exist as an inheritance hieracy, rooted in things and events.

**Things** describe real-world objects like ``people``, ``Companies``, ``Assets``, ``Court Cases``. You can think of things as entities. 

**Intervals** are ``business interests``, ``court cases``, ``sanctions``, and ``transactions`` and are useful for linking entities together, possibly over time.

Below is an interactive graph view of FMT ontology.

<iframe class="iframe" src="https://service.tib.eu/webvowl/#iri=https://alephdata.github.io/followthemoney/ns/ftm.xml" width="500px" height="500px" width="100%" title="Interactive Schema of FMT ontology" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


Once you have an ontology that structures your domain and its objects and relations, you can build a taxonomy to describe and group your information.

#### Build a taxonomy

While an ontology is a formal representation of knoweldge that defines concepts and relationships within a domain in a structured way, a taxonomy concerns the classification of entities based on their characteristics. 

Taxonomies are used to group types of entities into categories. 

For example, when we talk about associations and relationships in the sanctions space, we need ways of describing the type of entity or relationship. 

An associated entity could be an entity type: person, organisation, or vessel. If we know that our entity is a person, we can class his or her relationship to the sanctioned entity.

**Taxonomy of relationships**

| Relationship           | Definition                                                                           | Example                                                                 |
| --                     | ---                                                                                  | ---                                                                     |
| Employee               | The associated person is employed by the sanctioned individual                       | A nuclear engineer working for sanctioned company                       |
| Owned or controlled by | The associated organisation is owned or controlled by the entity it is connects with | OO NOVATEK-PERM is a subsidiary that is owned by sanctioned OAO NOVATEK |
| Family member          | An associate is a spouse, uncle, aunt, child, parent of sanctioned person            | Asma al-Assad is the spoise od Bashar al-Assad                          |


Having a taxonomy is crucial to investigations. A good taxonomy lets investigators describe and filter the information they're collecting. 


### Collect data

Global sanctions regimes vary as some countries implement and enforce the sanctions of international organisations such as the EU and the UN while others develop their own sanctions programs with their own sanctions lists. 

The first step in researching sanctioned entities is knowing which ones appear on an official sanctions list. 

#### Key sanctions lists

Government and finanical authorities maintain targeted sanctions lists. These lists are often available online and the lists evolve quickly.



- **UN sanctions list** is also known as the [UNSC Consolidated List](https://www.un.org/securitycouncil/content/un-sc-consolidated-list). It consists of one list of individual targets and one list of entities and group targets. UN sanctions are imposed by UN security council resolutions when the council determines a country is in breach of international law.
- **US sanctions** are the most influential global sanctions regime and consists of multiple sanctions lists. The Office of Foreign Assets Control, OFAC, maintains its primary sanctions lists. 
  - The [Specially Designated Nationals (SDN)](https://sanctionslist.ofac.treas.gov/Home/SdnList) list sanctions individuals and companies. 
  - The [Consolidated Sanctions List](https://sanctionslist.ofac.treas.gov/Home/ConsolidatedList) contains sanctions information not included in the SDN list. 
- **UK sanctions** are enforced by the Office of Financial Sanctions Implementations (OFSI) and Her Majesty's Treasury (HTM). Accordingly, UK firms must screen against UK Sanctions List.
- **Australia sanctions** are implemented by the Australian Sanctions Office (ASO) and the Department of Foriegn Affairs and Trade (DFAT). These two deparments implement Australia's sanctions regime and firms must screen against Consolidated List of sanctions. 
- **Canada sanctions** are implemented under the Special Economic Measures Act (SEMA) and the Justice for Victims of Corrupt Foreign Officials Act (JVCFO). Canadian sanctions are on the [Consolidated Canadian Autonomous Sanctions List]. 
- **Japan sanctions** are issued under the authority of the Foreign Exchange and Foreign Trade Act (FEFTA) and implemented by the Ministry of Economy, Trade, and Industry and the Ministry of Finance. Japan works with the UN, the US, and the EU in compiling its sanctions.
- **China sanctions** are issued by the Chinese Ministry of Foreign Affairs and, since 2020, China's Ministry of Commerce has developed new sanctions regulations designed as a response to Western sanctions. In China, there is the Unreliable Entity List (UEL) and rules the Anti-Foreign Sanctions Law and the Blocking Rules. 


#### Data in key sanctions lists

Sanctions lists are useful primary sources. They help investigators identify who's who in the sanctions space and serve as an excellent stepping stone to identifying associates and enablers of sanctioned entities. 

Common information about sanctioned entities include:
- ``name`` 
- ``alias``
- ``nationality``
- ``passport number`` 
- `country of birth`
- `reason for being sanctioned` 

Sanctions lists are usually strucuted xml, csv or html format, but can come as unstructured pdfs that require manual extraction. Below is an extract from the UNSC Consolidated List.

> iTAi.007 Name: 1: ABDUL LATIF 2: MANSUR 3: na 4: na
Name (original script): عبد اللطيف منصور
Title: Maulavi Designation: Minister of Agriculture under the Taliban regime DOB: Approximately 1968 POB: Zurmat District, Paktia Province, Afghanistan Good quality a.k.a.: a) Abdul Latif Mansoor b) Wali Mohammad Low quality a.k.a.: na Nationality: Afghanistan Passport no: na National identification no: na Address: na Listed on: 31 Jan. 2001 ( amended on 3 Sep. 2003, 18 Jul. 2007, 21 Sep. 2007, 13 Feb. 2012, 18 May 2012, 22 Apr. 2013 ) Other information: Taliban Shadow Governor for Logar Province as of late 2012. Believed to be in Afghanistan/Pakistan border area. Belongs to Sahak tribe (Ghilzai). Review pursuant to Security Council resolution 1822 (2008) was concluded on 27 Jul. 2010. INTERPOL-UN Security Council Special Notice web link:https://www.interpol.int/en/How-we-work/Notices/View-UN-Notices-Individuals click here


These data points present in sanctions lists are important points of reference. Investigators can use data points like alias and age or passport number to confirm if the person on the sanctions list is the same as the person in a company register. 

#### Limit of primary sources

Investigating if an individual, vessel, or organisation is subject to financial sanctions is relatively straightforward. You usually return a match after a quick search on one of the sanctions lists.

The job of investigating is harder when we want to identify associates or entities enabling the sanctioned person or organisation. 

For example, identifying if an entity is sanctioned becomes harder when shell companies are involved. 

A  company may not show up as sanctioned on sanctions lists, but if a sanctioned entity owns 51% of the company then both the company and the sanctioned entity are sanctioned. This is the OFAC50 rule. 

Sanctions lists are excellent primary sources but investigations require a holistic approach. For this, we turn to other sources. 


#### Data Enrichment

We use othersources as part of investigations to enrich the data we collect from sanctions lists. 


Sources commonly used in investigations range from ownership and land registries to leaked documents, mentions in media, and aggreggated data in databases.

An excellent example of how investigators draw on open sources is the [investigation](https://www.thebureauinvestigates.com/stories/2024-05-10/leaked-documents-reveal-abramovichs-ongoing-vitesse-connection/) into Roman Abramovich and his financial dealings with the Dutch football club, Vitesse.

Roman Abramovich was subjected to UK and EU sanctions following Russia's invasion of Ukraine.

By using the Oligarch Files, a cache of leaked data originating from MeritServus, an offshore service provider based in Cyprus, investigators at the Bureau of Investigative Journalism (TBIJ) and the Guardian were able to reveal that Roman Abramovich, who then owned Chelsea football club, was the source of all money used to fund the Dutch football club, Vitesse. 

The Guardian found that Abramovich had covertly funded the 2010 acquisition of Vitesse Arnhem via a network of offshore entities before channelling at least 117 million euros to the club. 

In this case, their [analysis](https://www.thebureauinvestigates.com/stories/2023-03-29/roman-abramovich-bankrolled-major-dutch-club-while-chelsea-owner/) of the  Oligarch Files helped investigators enrich the data they already had on Abramovich, leading them to identify 6 companies associated with Abramovich and Vitesse.

#### Entity Resolution

In AML and illicit finance, we are always striving toward a source of truth. We enrich our data in the hopes of getting to that truth. 

Enriching data requires that investigators perform entity resolution to ensure that they are correctly linking records together. 

Enity resolution is broadly speaking the process of identifying data records in a source across multiple sources that refer to the same entity. 

You can resolve entities manually, usually by looking at the similarity of their names, age, height, and other data points. As you read these records, you understand if the sources describe the same two peope.

If you're certain the records match, you can merge the records and enrich  your entity.

Manually resolving entities is a time-consuming task, so investigators naturally rely on data science to combine records.

In the world of data, entity resolution or record matching also goes by the name of some of its techniques, like fuzzy matching, merge purge, data matching or idenity resolution.

Through entity resolution, we can identify if two records refer to the same entity and enrich our understanding of that data. Once we have a source of truth, the next step is understanding how to use it. 

### Network Analysis

Data dumps are rarely useful on thier own and the process of collecting, enriching and resolving data should yield a big set of data. 

Network analysis is one of the techniques that investigators can use to extract useful information from big data. 

This useful information teaches us about network risks and broader trends in how illict finance is organised.

In the investigation into Roman Abramovich, investigators identfied 6 companies associated with him and the football club Vitesse.

<iframe src="https://embed.kumu.io/7839eb07b6212cd1cdbe0acb1267f260#untitled-map" width="100%" height="500px" class='iframe'></iframe>


By drawing the connections between these entities, we learn who's connection to whom and how sanctioned individuals like Roman Abramovich use offshore networks to circumvent sanctions.


{{% /steps %}}


## Recap

Every investigation requires four simple steps to be successful. Before you start, you should decide on a way of first describing objects and relations and then set up a system of classifying these objects. Once ready, start by identifying and collecting information from reliable sources, then, branch out by collecting data from as many relevant sources as possible. Use entity resolution to match records and find useful insights in your data with network analysis. 



