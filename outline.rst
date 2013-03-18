:title: Social Network Analysis, PyData 2013 Tutorial by Kat Chuang
:css: slides.css

----

:div: firstslide

PyData 2013 Tutorial:
=====================

Social Network Analysis
========================

~
----------------

Katherine Chuang
.................

@katychuang
............

----

1. Introduction to SNA Theory
================================

----

**SNA is a powerful research technique.**

#. Tracking health epidemics (i.e. spread of infections)
#. Measuring an online community (i.e. conversation patterns)
#. Graphically display data

.. image :: images/virus.png
	:width: 100%

----

.. image :: images/small_undirected_network_labeled.png

**SNA is essentially graph theory. A network is made up of nodes and edges.**

----

.. image :: images/small_directed_network_labeled.png

**Edges can have direction.**

----

.. image :: images/graph_example.jpg

**Edges can be weighted**

----

.. image :: images/sna-roles.jpg
	:width: 90%

**Nodes can be of a type (social roles)**

----

Describing individual nodes
================================================

* Centrality - an individual node's number of links

* Degree – number of links from and to the node.

* Betweenness – The extent to which an individual node is 'between' other nodes

* Closeness – The degree to which an individual is near all other individuals in a network (directly or indirectly).

----

Describing subgroups
============================

* Cliques - a group where every node is directly connected to each other

* Clustering Coefficient - the average density of a subgroup

* Blockmodels - a cluster of users based on type of relationship, i.e. novices

* Eigenvector Centrality - highlights the importance of users in a network

----

.. image :: images/qacomm.jpg

.. code ::

	Yellow = experts answering questions; Red = novices

	http://lithosphere.lithium.com/t5/science-of-social-blog/
	Social-Graphs-The-Art-and-the-Insights/ba-p/5713

----

.. image :: images/discussioncomm.jpg

.. code ::

	Lots of dialogue back and forth between users

	http://lithosphere.lithium.com/t5/science-of-social-blog/
	Social-Graphs-The-Art-and-the-Insights/ba-p/5713

----

.. image :: images/techcomm.jpg

.. code ::

	Q&A + Discussion

	http://lithosphere.lithium.com/t5/science-of-social-blog/
	Social-Graphs-The-Art-and-the-Insights/ba-p/5713

----

.. image :: images/enthcomm.jpg

.. code ::

	Experts are scattered in community

	http://lithosphere.lithium.com/t5/science-of-social-blog/
	Social-Graphs-The-Art-and-the-Insights/ba-p/5713



----

Social Interaction Design
====================================

.. image :: images/ui/myspace-profile.BMP

UI design for self-presentation
----------------------------------
and interacting with others
--------------------------------------------------------

----

It's your social history...
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
#. NetworkX magic
#. Export image

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
	print g.neighbors("B") #['A']

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

**Time for magic tricks.**

.. code :: python

	# Verify your python installation
	$ python --version

	# Make sure networkx can be used.
	$ python -c "import networkx;"

	# Open up your text editor

----

3. Let's code!
=========================================

----

**Open up a text editor**

.. image :: images/ui/pythonanywhereeditor.png
	:width: 90%

.. code ::

	PythonAnywhere.com has one built in.

----

**Exercise..**

* Importing data
* Plot data points
* Export images

-----

Download: http://bit.ly/15WDFW9
================================

.. code :: python

	# Script:
	https://github.com/katychuang/PyData2013-SNATutorial/blob/master/virus.py

	# Documentation:
	http://networkx.github.com/documentation/latest/contents.html

	# MatPlotLib:
	http://matplotlib.org/users/gridspec.html

----

"Social interaction design is the application of levers to steer and guide emerging social practices"  *-- Adrian Chan, Gravity7*

----

Questions?
------------------

* Email: katychuang@acm.com
* Twitter: @katychuang
* Code: github.com/katychuang
