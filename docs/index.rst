.. Azkaban CLI documentation master file, created by
   sphinx-quickstart on Thu Mar 14 14:47:18 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.



Azkaban CLI
===========


.. image:: https://travis-ci.com/globocom/azkaban-cli.svg?branch=master
   :target: https://travis-ci.com/globocom/azkaban-cli
   :alt: Build Status


CLI for Azkaban 3 API access and flow upload.

Installation
------------

Please virtualenv or conda env on this, example as follows

.. code-block:: sh

   ### Building virtualenv
   virtualenv azkaban_cli

   ### Activating virtualenv
   source azkaban_cli/bin/activate

   ### Installing Azkaban CLI
   pip install azkaban_cli

Usage
-----

Activate your virtualenv and call ``azkaban``

.. code-block:: sh

   $ azkaban --help
   Usage: azkaban [OPTIONS] COMMAND1 [ARGS]... [COMMAND2 [ARGS]...]...

   Options:
     --version  Show the version and exit.
     --help     Show this message and exit.

   Commands:
     add_permission        Add a group with permission in a project
     change_permission     Change a group permission in a project
     create                Create a new project
     delete                Delete a project
     execute               Execute a flow from a project
     fetch_flow_execution  Fetch a flow execution
     fetch_jobs_from_flow  Fetch jobs of a flow
     fetch_projects        Fetch all project from a user
     fetch_sla             Fetch the SLA from a schedule
     login                 Login to an Azkaban server
     logout                Logout from Azkaban session
     remove_permission     Remove group permission from a project
     schedule              Schedule a flow from a project with specified cron...
     unschedule            Unschedule a flow from a project
     upload                Generates a zip of path passed as argument and...

Examples
--------

Making Login
^^^^^^^^^^^^
This command will login cache information and then won't need to be run again


.. code-block:: sh

   azkaban login --host https://azkaban.your_company.com

Contribute
----------

For development and contributing, please follow `Contributing Guide <https://github.com/globocom/azkaban-cli/blob/master/CONTRIBUTING.md>`_ and ALWAYS respect the `Code of Conduct <https://github.com/globocom/azkaban-cli/blob/master/CODE_OF_CONDUCT.md>`_


API Methods
===========

login
-----
.. code-block:: classazkaban_cli.azkaban.Azkaban.login
Login command, intended to make the request to Azkaban and treat the response properly

This method validate the host, make the request to Azkaban, and evaluate the response. If host, user or password is wrong or could not connect to host, it returns false and do not change the host and session_id attribute from the class. If everything is fine, saves the new session_id and corresponding host as attributes in the class and returns True

Parameters
host (str) – Azkaban hostname

user (str) – Username to login

password (str) – Password from user

Raises
LoginError – when Azkaban api returns error in response


logout
------
.. autoclass:: azkaban_cli.azkaban.Azkaban.logout


upload
------
.. autoclass:: azkaban_cli.azkaban.Azkaban.upload


create
------
.. autoclass:: azkaban_cli.azkaban.Azkaban.create


delete
------
.. autoclass:: azkaban_cli.azkaban.Azkaban.delete

add_permission
--------------
.. autoclass:: azkaban_cli.azkaban.Azkaban.add_permission

change_permission
-----------------
.. autoclass:: azkaban_cli.azkaban.Azkaban.change_permission

remove_permission
-----------------
.. autoclass:: azkaban_cli.azkaban.Azkaban.remove_permission

execute
-------
.. autoclass:: azkaban_cli.azkaban.Azkaban.execute

fetch_projects
--------------
.. autoclass:: azkaban_cli.azkaban.Azkaban.fetch_projects

fetch_sla
---------
.. autoclass:: azkaban_cli.azkaban.Azkaban.fetch_sla

fetch_flow_execution
--------------------
.. autoclass:: azkaban_cli.azkaban.Azkaban.fetch_flow_execution

fetch_jobs_from_flow
--------------------
.. autoclass:: azkaban_cli.azkaban.Azkaban.fetch_jobs_from_flow

schedule
--------
.. autoclass:: azkaban_cli.azkaban.Azkaban.schedule

unschedule
----------
.. autoclass:: azkaban_cli.azkaban.Azkaban.unschedule



