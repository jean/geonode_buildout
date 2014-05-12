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
    ~/venv/geonode$ ./bin/buildout

    # To build different sets of components:
    ~/venv/geonode$ ./bin/buildout -N -c geonode-django.cfg 
    ~/venv/geonode$ ./bin/buildout -N -c postgis.cfg 
    ~/venv/geonode$ ./bin/buildout -N -c geoserver.cfg 
    ~/venv/geonode$ ./bin/buildout -N -c nginx.cfg 

> **Note**: The ``-N`` option prevents buildout from checking for newer versions
  of eggs. In our case isn't really so important at the moment, just helps
  keeps things predictable. 

> **Note**: the individual buildouts will leave only the set in that config,
  nuking the rest. To pick and choose parts, edit buildout.cfg

Coming soon, and caveats
------------------------

I'm making this work before I make it pretty.
The current setup may have local paths (e.g. my download-cache location)
and brain damage (e.g. the stub django project dir created at the buildout
root).

Buildout configs for nginx, uwsgi, tomcat, supervisord. etc. follow.
