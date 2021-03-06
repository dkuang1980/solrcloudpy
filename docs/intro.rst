Intro
===========

``solrcloudpy`` is a python library for interacting with SolrCloud. This library aims to take advantage of the following features of Solr:

* Distributed indexing and searching and transparent failover
* Full JSON api
* Centralized index management
* Near-realtime search

The API is meant to be close to ``pymongo``'s API, where one can access collections as simple attributes or dictionary keys.  

::

     >>> conn = SolrConnection(["localhost:9983","localhost:8984"])
     >>> conn.create('test1',num_shards=1,replication_factor=2)
     
     # Access an existing collection
     >>> conn.test_collection.search(q='query')
     {   
         "response": "SolrResponse << {'start': 0, 'numFound': 0, 'docs': []} >>"
     }
     >>> conn["test_collection"].search(q='query 2')
     {   
         "response": "SolrResponse << {'start': 0, 'numFound': 0, 'docs': []} >>"
     }

Pre-requisites
----------------
You will need to run Solr in "cloud" mode to use this library. To use
the console, you will need to install the `ipython` package.

Installation
--------------

``solrcloudpy`` is available on pypi: ``pip install solrcloudpy``. To
install the development version:

``pip install
git+https://github.com/dfdeshom/solrcloudpy.git#egg=solrcloudpy``


Contributing
-------------

Send pull requests!
