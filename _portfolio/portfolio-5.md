---
title: "Judgements Anonymization"
excerpt: "We are going to anonymize judgements from Corte di Cassazione using state of the art NLP.<br/><img src='/images/trumpbiden.png'>"
collection: portfolio
---

Project made with Monia Bennici.
#### Main skills learned
* Data Scraping using BeautfulSoup and Selenium
* Network analysis using CDlib, Networkx and NDlib
* Implementation of spectral algorithms for Community Discovery


#### Introduction

In the following we will analyse the network created from
Airbnb, capturing the main measures and trying to understand some aspect, applying some community discovery
techniques and the simulation of diffusion model. In particular, we will implement, apart from the algorithms given in the
libraries, a new algorithm based on the spectral clustering.
Moreover, we would like to capture the so called "sockpuppet" phenomenon, that is all users that create more than one
account to deceive the restrictions given in the platform. All
the notebooks are stored in github repositories.


Airbnb is one of the biggest platform of house sharing, in
which people can rent rooms of their own house for short
terms, that was born in order to let them make some money.
Of course this is a problem for most of the hotels owners
and this is the reason why some cities decided to restrict the maximum amount of time a host can rent his house, that
is usually 60-90 days per year depending on the city. Our
network is created using as nodes hosts and guests registered
in the platform in the area of Amsterdam. In particular, hosts
are those who rent the rooms, guests are users who pay to
use the room and leave the reviews of their experience in
that house and with that host. So, our net is a bipartite graph,
in which every guest can be connected only to hosts and
the edge represent the number of time the guest has left a
review.
After collecting the useful data we compared our network
with random networks and then we did 3 analytical tasks.
