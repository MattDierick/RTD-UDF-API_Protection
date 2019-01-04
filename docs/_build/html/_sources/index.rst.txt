Introduction
============

This documentation explains how to demonstrate the UDF API Protection blueprint. This blueprint includes :

* 1 x BIGIP with APM provioned
* 1 x Windows Client with Postman
* 1 x Linux server with Loopback nodeJS application

**What is Loopback ?**

Loopback is a NodeJS application that creates an API Server in few minutes. https://loopback.io/
With few command lines, you can create your own API and publish it.

**Quick demonstration video**

This video demonstrate the demo script but does not show how to create the API.

.. raw:: html

    <div style="text-align: center; margin-bottom: 2em;">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/-2ndGH9Dp1Q" frameborder="0" allowfullscreen></iframe>
    </div>


**Start the environment**

Connect in SSH into the Linux server. And launch these commands :

.. sourcecode:: bash

    $ sudo su
    $ cd /root/My_Movies/
    $ node .

The nodeJS server should start and should see these lines :

.. sourcecode:: bash

    Web server listening at: http://localhost:3000
    Browse your REST API at http://localhost:3000/explorer


**User documentation**

.. toctree::
    :maxdepth: 2

    API_server_configuration/Create_your_own_API.rst
    BIGIP Configuration/Configure_API_protection_profile.rst

