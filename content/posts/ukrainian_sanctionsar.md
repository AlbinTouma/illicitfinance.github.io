---
title: How investigators find out who's who in sanctions investigations
date: 2024-04-19
draft: false
---

We often talk about sanctions in the context of efficiency or individual cases. Who's who in the sanctions space has, as a result, become elusive when there are characteristics, data sets, and methods of revealing sanctioned entities and their networks. 

We'll explore 4 steps in the research process, from the design of research methods to the collection, analysis, and sharing of intelligence.



{{% steps %}}

### Research Design

#### Ontology

The first step is to settle on an ontology that describes entities and relations between them. We recommend Follow the Money's ontology. 

A big part of researching who's who in the sanctioned space is knowing how to describe entities and relations beetween them. In industry, we describe our domain and its objects in an [ontology](https://en.wikipedia.org/wiki/Ontology). 

An ontology is a formal naming and definition of categories, properties, and relations betweeen concepts, data, or entities.

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


### Data Collection

#### Primary sources

It is relatively straightforward to find out if an individual, vessel, or organisation is subject to financial sanctions. You usually return a match after a quick search of the entity's name or alias on consolidated sanctions lists such as [the Office of Financial Sanctions Implementations](https://www.gov.uk/government/publications/financial-sanctions-consolidated-list-of-targets). 

Identifying if an entity is sanctioned becomes harder when shell companies are involved. A company may not show up as sanctioned, but it is 51% owned by another company which is sanctioned. This means both companies are sanctioned. 




<!---Enrichment --->
<!---Network Analysis -->

{{% /steps %}}



