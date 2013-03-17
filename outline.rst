:title: Advanced Social Network Analysis, PyData 2013 by Kat Chuang
:css: tutorial.css

----

Social Network Analysis
==========================

*from henceforth referred to as SNA*

----

1. Introduction to Theory
==========================

----

**SNA is a powerful research technique.**

- Tracking health epidemics (i.e. addictions, obesity)
- Crisis Management
- Social Support Networks
- Social Media Usage

----

.. image :: images/small_undirected_network_labeled.png

**SNA is essentially graph theory. A network is made up of nodes and edges.**

----

.. image :: images/small_directed_network_labeled.png

**A graph can be directed.**

----

.. image :: images/graph_example.jpg

**A graph can also be weighted**

----

**Networks can be described with following characteristics.**

* Density
* Centrality
* Cliques

----

**Here are some advanced network techniques**

* Blockmodels

----

Social Interaction Design Patterns
-----------------------------------

*(online presentation of self)*

- Friend List; Facets, friend groups, circles
- Liking vs Open text, voting
- Shopping, reviewing (best of and new)
- Classified listing, market place

----

Continued
========================================

*(interacting with others)*

- Data sharing (patients like me)
- Threaded messages, public vs private
- Press, blog coverage
- Knowledge sharing (books, music, pets)
- Conversation, announcements

----

"Social interaction design is the application of levers to steer and guide emerging social practices"
Letting users feel like it's their space

**Conversation Elements**

- personal information, stories
- advice, recommendations, reviews
- opinions, discussions

"SNA allows you to map these interactions"

----

Recap of the three areas


----

2. Introduction to Python and libraries
=========================================

----

* NetworkX (v1.7, networkx.github.com)
* LibSNA (v0.3, www.libsna.org)

----

NetworkX modules
================


----

LibSNA modules
================

.. code :: python

	calculateBetweenness(self)
		Calculate betweenness centrality.

	calculateCloseness(self)
		Calculate closeness centrality.

	calculateTotalDegree(self)
		Calculate total degree centrality.


----

3. Let's code!
=========================================

----

Exercises

* Importing data
* Summary information
* Calculations
* Advanced things
* Export data in text
* Export in images

-----

Examples

