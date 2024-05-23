---
theme: apple-basic

highlighter: shiki
lineNumbers: true
title: Abusing ActivityPub to federate game servers
info: |
  Abusing ActivityPub to federate game servers
  A deeper look into what powers the Social Web.
favicon: /images/fediverse-logo.png
drawings:
  persist: false
mdc: true
transition: slide-left
defaults:
  layout: default

layout: intro
---

# Abusing ActivityPub to federate game servers

## A deeper look into what powers the Social Web.

<div class="absolute bottom-10">
  <span class="font-700">
   iu.tech 2024
  </span>
</div>

---

# Who am I?

### Sebastian Di Luzio
- Senior Software Engineer @ Team Foundation, Edutech
- Enjoy playing videogames a lot
- Spend far too much of my free time on side projects

---
layout: image-right

image: /images/fediverse-logo.png
---

# What's this social web, or Fediverse?
- The Fediverse is a giant Network of social media services.
- There are platforms for microblogging, blogging, photoblogging, videohosting and much more and they are all interconnected, or federated.
- You only need one account to follow users on any of the platforms.
- Services in the Fediverse interact with each other using the ActivityPub protocol.



---
layout: image-right

image: /images/fedidb-software-distribution.png
---

# An alternative to centralized social media
<br>

## <mdi-mastodon class="text-6" /> Mastodon

- A microblogging platform
- Open source
- Became widely popular when Elon Musk took over Twitter
- The largest piece of software in the Fediverse
- 7.000.000+ users

---

# What do game servers have to do with this?

## Federation of Mastodon inspired this game.
How cool would it be if people hosted their own game servers and they could play with their friends from other servers?

## What's this game about

- It's more about playing around with interesting tech than building a game that is successful.
- It's also about getting tech savvy people to think about the social web
- I want people to build their own clients, and I want to see what they come up with.
- A small group of people cooperating on a shared goal.

---

# Gameplay TLDR
- Idle, Base Building, Coop Multiplayer
- You are a villager in a small village
- Your task is to build up your village
- You need resources to build
- You can generate a specific resource set based on your occupation
- You can trade resources with other players, and will need to do so to progress

---

# Original Federation
- Last year I built a simple federation system that worked
- Essentially, it was a simple push/pull system based on standardized events shared over REST
- It worked!
- It was boring and highly specific to this game

---

### I asked myself

# What if someone on Mastodon could follow my gameserver and get updates on what's happening in the game?

### It's really not necessary for the gameplay.

But it would be cool.

---

# Whats this ActivityPub thing?

- ActivityPub is an open, decentralized social networking protocol based on ActivityStreams and JSON-LD
- It provides a client/server API for managing content, as well as a federated server-to-server API for delivering notifications and content
- It's a W3C standard. If you don't know who they are, they are the people who define: HTML, CSS, XML, WebAssembly, WebRTC, SOAP, and many more
- It's what powers the Fediverse


---

# ActivityStreams (2.0)

- Also a W3C standard
- Specifies underlying schemata used in ActivityPub
- Includes things like: Object, Actor, Activity, Collection, Link
- is implemented as serialized JSON-LD


---

# JSON-LD

JSON for Linking Data

JSON-LD is a lightweight Linked Data format.

## Linked Data
Linked Data empowers people that publish and use information on the Web.

It is a way to create a network of standards-based, machine-readable data across Web sites.


---
layout: two-cols-header
---
::left::
Example JSON-LD object:
```json
{
  "@context": 
    "https://json-ld.org/contexts/person.jsonld",
  "@id": 
    "http://dbpedia.org/resource/John_Lennon",
  "name": "John Lennon",
  "born": "1940-10-09",
  "spouse": 
    "http://dbpedia.org/resource/Cynthia_Lennon"
}
```
::right::

https://json-ld.org/contexts/person.jsonld:

```json
{
  "@context": {
      "Person": "http://xmlns.com/foaf/0.1/Person",
      "xsd": "http://www.w3.org/2001/XMLSchema#",
      "name": "http://xmlns.com/foaf/0.1/name",
      "born":
      {
         "@id": "http://schema.org/birthDate",
         "@type": "xsd:date"
      },
      "spouse":
      {
         "@id": "http://schema.org/spouse",
         "@type": "@id"
      },
   }
}
```


---

# ActivityPub

- Activities
- Objects



---

# Activities


- Create
- Update
- Delete
- Follow
- Like
- Accept
- ...

---

# Objects

- another Activity
- a Note
- an Actor
- ...



---

# Actor


- Representation of a "User"
- can be one per server, or many per server
- can be a person, an organization, a bot, ...
- is the author/owner of activities and objects
- has an inbox and outbox

---

# Inbox/Outbox

Sounds like email? It is like email.



---

# header


content

---
layout: two-cols-header
---

# Follow me for more

::left::

#### <mdi-mastodon class="text-4" /> @maybeanerd@bumscode.com
#### <mdi-github class="text-4" /> maybeanerd
#### <mdi-web class="text-4" /> diluz.io/sebastian
#### <mdi-linkedin class="text-4" /> sebastian-di-luzio

::right::

#### <mdi-email class="text-4" /> give-me-feedback-on-the-abusing-activity-pub-to-federate-game-servers-presentation-please@diluz.io