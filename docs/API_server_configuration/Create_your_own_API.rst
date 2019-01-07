Create your own API for an inventory (movie, DVD, books ...)
============================================================

If you want, you can create your own API instead of using my Movie inventory API.


Create the API project
----------------------

First of all, you need to create the project. To do so, go to /root directory, and launch the following commands

.. sourcecode:: bash

    $ lb
    ? What's the name of your application? (root) ENTER A NAME
    ? Enter name of the directory to contain the project: PRESS ENTER TO SELECT DEFAULT FOLDER

    ? Which version of LoopBack would you like to use? (Use arrow keys)
        ❯ 3.x (Active Long Term Support)  <-- SELECT 3.x
        2.x (Maintenance Long Term Support)

    ? What kind of application do you have in mind?
        api-server (A LoopBack API server with local User auth)
        ❯ empty-server (An empty LoopBack API, without any configured models or datasources) <-- SELECT EMPTY SERVER
        hello-world (A project containing a controller, including a single vanilla Message and a single remote method)
        notes (A project containing a basic working example, including a memory database)

Now the project is created. Go into the new directory.


Connect the datasource
----------------------

Next, you need to specify where to store the datas. By default, there are stored in the memory. We have a MonogDB running in the same server. Let's connect to it.

.. sourcecode:: bash

    $ lb datasource
    ? Enter the datasource name: My_MongoDB
    ? Select the connector for My_MongoDB:
        ❯ MongoDB (supported by StrongLoop)    
    ? Connection String url to override other settings (eg: mongodb://username:password@hostname:port/database):
    ? host: localhost
    ? port: 27017
    ? user:
    ? password: [hidden] <-- NO PASSWORD
    ? database: My_MongoDB
    ? Install loopback-connector-mongodb@^3.6.0 (Y/n) Y


Create the model
----------------

Last step is to create the model of the API. 

.. sourcecode:: bash

    $ lb model
    ? Enter the model name: My_DVD
    ? Select the datasource to attach My_DVD to: My_MongoDB (mongodb)
    ? Select models base class PersistedModel
    ? Expose My_DVD via the REST API? Yes
    ? Custom plural form (used to build REST URL):
    ? Common model or server only? common
    Let's add some My_DVD properties now.

    Enter an empty property name when done.
    ? Property name: name
    ? Property type: string
    ? Required? Yes
    ? Default value[leave blank for none]:

Repeat theses steps for every property (description, rate, location ...) When finished, just click ENTER

Test your API
-------------

Start the server, and test it.

.. sourcecode:: bash

    $ node .


Connect in RDP to the Windows Client and open chrome. Connect to http://10.1.20.5:3000/explorer
You should see your API. Now, you can add entries in the POST /movies (or any other name you put)

.. image:: /images/Loopback_UI.png
    :align: center

Test your API with Postman. Open Postman and do a GET to the right URI

.. image:: /images/Postman_UI.png
    :align: center


.. note:: Congratulation, your API is up and running, but there is neither protection nor authentication in front of it. Connect to the BIGIP and configure the API protection profile.
