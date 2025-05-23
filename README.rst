
# DataCore
======================================

**DataCore** is an advanced database system project that provides an in-depth exploration of complex database systems and their applications. This repository contains various implementations, optimizations, and features for advanced database management, querying, and performance analysis. The project aims to provide robust solutions to modern database problems using cutting-edge techniques.

With an emphasis on scalability, performance, and reliability, this project is ideal for anyone looking to explore advanced concepts in database design, indexing, query optimization, and more.


cryptoCMD: cryptoCurrency Market Data


.. image:: https://img.shields.io/pypi/v/cryptoCMD.svg
    :target: https://pypi.python.org/pypi/cryptoCMD

.. image:: https://travis-ci.org/guptarohit/cryptoCMD.svg?branch=master
    :target: https://travis-ci.org/guptarohit/cryptoCMD
    
.. image:: https://app.fossa.io/api/projects/git%2Bgithub.com%2Fguptarohit%2FcryptoCMD.svg?type=shield
    :target: https://app.fossa.io/projects/git%2Bgithub.com%2Fguptarohit%2FcryptoCMD?ref=badge_shield
    :alt: FOSSA Status

.. image:: https://img.shields.io/pypi/l/cryptoCMD.svg
    :target: https://github.com/guptarohit/cryptoCMD/blob/master/LICENSE

.. image:: https://img.shields.io/pypi/pyversions/cryptoCMD.svg
    :target: https://pypi.python.org/pypi/cryptoCMD

.. image:: https://pepy.tech/badge/cryptoCMD
    :target: https://pepy.tech/project/cryptoCMD
    :alt: Downloads

.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
    :target: https://github.com/ambv/black
    :alt: Code style: black

Cryptocurrency historical market price data scraper written in Python.


Installation
------------

::

    $ pip install cryptocmd

to install from the latest source use following command

::

    $ pip install git+git://github.com/guptarohit/cryptoCMD.git


Usage
------
=====================
CoinMarketCap Scraper
=====================

Following methods are available to get data in multiple formats from https://coinmarketcap.com

To get all time historical data of a cryptocurrency
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code:: python

    from cryptocmd import CmcScraper

    # initialise scraper without passing time interval
    scraper = CmcScraper('XRP')

    # data as list of list in a variable
    headers, data = scraper.get_data()

    # export the data as csv file, you can also pass optional name parameter
    scraper.export_csv('xrp_all_time.csv')

    # Pandas dataFrame for the same data
    df = scraper.get_dataframe()

To get data of a cryptocurrency for some days
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code:: python

    from cryptocmd import CmcScraper

    # initialise scraper
    scraper = CmcScraper('XRP', '15-10-2017', '25-10-2017')

    # get data as list of list
    headers, data = scraper.get_data()

    # export the data to csv
    scraper.export_csv()

    # get dataframe for the data
    df = scraper.get_dataframe()


Following are the columns of the data
"""""""""""""""""""""""""""""""""""""
``Date, Open, High, Low, Close, Volume, Market Cap``


Acknowledgements
----------------
The data is being scrapped from `coinmarketcap <https://coinmarketcap.com>`_ :v: and it's `free <https://coinmarketcap.com/faq/>`_ to use. :tada:

Contributing
------------

Feel free to make a pull request! :octocat:

License
-------

.. image:: https://app.fossa.io/api/projects/git%2Bgithub.com%2Fguptarohit%2FcryptoCMD.svg?type=large
    :target: https://app.fossa.io/projects/git%2Bgithub.com%2Fguptarohit%2FcryptoCMD?ref=badge_large
    :alt: FOSSA Status
