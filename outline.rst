:title: Advanced Social Network Analysis, PyData 2013 by Kat Chuang
:css: tutorial.css

----

:div: firstslide

Advanced Tutorial:
==================

Social Network Analysis
========================

~
----------------

presented at PyData 2013
.........................

by Katherine Chuang
...................

----

1. Introduction to SNA Theory
================================

----

**SNA is a powerful research technique.**

#. Tracking health epidemics (i.e. addictions, obesity)
#. Measuring an online community

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

Social Roles
============

.. image :: images/sna-roles.jpg

----

Social Network Metrics for individual nodes
================================================

* Centrality: an individual node's number of links

* Degree – The count of the number of ties that an individual has to other nodes in the network.

* Betweenness – The extent to which an individual sits between other nodes in the network.

* Closeness – The degree to which an individual is near all other individuals in a network (directly or indirectly).

----

Other metrics
================

* Blockmodels
* Eigenvector values

----

Social Interaction Design
====================================

.. image :: images/ui/myspace-profile.BMP

online presentation + interacting with others
--------------------------------------------------------

----

Social History has metadata
----------------------------

.. image :: images/ui/markztimeline.jpg
	:width: 90%

----

Design patterns
========================================

- Discussion threads, reviews, classified listing, news, data sharing
- Responding via likes, votes, free text
- Each unit of analysis has a sender and receiver (2 nodes, 1 edge)

.. image :: images/ui/github_social_buttons.png

----

Recap: Map online conversations
---------------------------------

.. image :: images/social-network_illu_farbig.png

----


.. image :: images/ui/JH-Blog-Writers-Back-in-5-minutes.gif

**please ensure you have Python v2.7 and Networkx v1.7**

.. code :: python

	$ pip freeze

	# alternatively, if you do not have these installed,
	# you can create an account on pythonanywhere.com


----

2. Introduction to NetworkX
=========================================

----

NetworkX v1.7
=============

.. image :: images/ui/networkx-home.png
    :width: 90%

----

Workflow
=========

#. Read in raw data
#. Convert to NetworkX graph object
#. NetworkX magic
#. Output data in json format
#. D3.js magic (optional)

----

NetworkX basics
================

.. code :: python

	import networkx 			# import library

	g = networkx.Graph()			# create undirected graph object

	g.add_edge(1,2)				# add data
	g.add_edge(3,1)
	g.add_node(4)

	print g.number_of_nodes() 		# 4
	print g.nodes()				# [1, 2, 3, 4]

	print g.number_of_edges()		# 2
	print g.edges()				# [(1, 2), (1, 3)]

----

NetworkX Directed Graph
==========================

.. code :: python

	g = networkx.DiGraph()	# directed graph
	g.add_edges_from([("A","B"), ("C","A")])
	print g.in_degree(with_labels=True) # {'A': 1, 'C': 0, 'B': 1}

	print g.out_degree(with_labels=True) # {'A': 1, 'C': 1, 'B': 0}

	print g.neighbors("A") 	# ['B']
	print ug.neighbors("B") #['A']

----

NetworkX modules
================

.. code :: python

	print g.degree()	# {1: 2, 2: 1, 3: 1, 4: 0}

	print networkx.betweenness_centrality(g)
				# {1: 0.3333333333333333, 2: 0.0, 3: 0.0, 4: 0.0}

	print networkx.degree_centrality(g)
				# {1: 0.6666666666666666, 2: 0.3333333333333333,
				# 3: 0.3333333333333333, 4: 0.0}

----

.. image :: images/ui/JH-Blog-Writers-Back-in-5-minutes.gif

.. code :: python

				# are you ready?

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

"Social interaction design is the application of levers to steer and guide emerging social practices"  *-- Adrian Chan, Gravity7*

----

Questions?
------------------

* Email: katychuang@acm.com
* Twitter: @katychuang
* Code: github.com/katychuang
