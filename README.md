geonode_buildout
================

Configuration to build a complete geonode environment using zc.buildout

How use this
------------

Get the buildout somewhere comfortable::

    ~/venv$ git clone git@github.com:jean/geonode_buildout.git geonode

Turn that directory into a virtualenv::

    ~/venv/geonode$ virtualenv .

Install buildout::

    ~/venv/geonode$ ./bin/pip install zc.buildout

Edit `config.cfg` to adjust ports and filesystem layout to your preferences
*(incomplete)*.

Start building::

    # To build everything:
    ~/venv/geonode$ ./bin/buildout -Nv

> **Note**: The ``-N`` option prevents buildout from checking for newer versions
  of eggs. In our case isn't really so important at the moment, just helps
  keeps things predictable. 

Coming soon, and caveats
------------------------

I'm making this work before I make it pretty.
The current setup may have local paths (e.g. my download-cache location), 
and brain damage (e.g. the stub django project dir created at the buildout
root).

Buildout configs for nginx, uwsgi, tomcat, supervisord aren't tested yet.
