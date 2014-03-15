Bitmask
=======

*your internet encryption toolkit*

.. image:: https://pypip.in/v/leap.bitmask/badge.png
        :target: https://crate.io/packages/leap.bitmask
.. image:: https://pypip.in/d/leap.bitmask/badge.png
.. image:: http://lemur.leap.se:8010/png?builder=bitmask-linux-quick


**Bitmask** is the multiplatform desktop client for the services offered by
`the LEAP Platform`_.

It is written in python using `PySide`_ and licensed under the GPL3.
Currently we distribute pre-compiled `bundles`_ for Linux, OSX and Windows.

.. _`PySide`: http://qt-project.org/wiki/PySide
.. _`the LEAP Platform`: https://github.com/leapcode/leap_platform
.. _`bundles`: https://downloads.leap.se/client/


Read the Docs!
------------------

The latest documentation is available at `Read The Docs`_.

.. _`Read The Docs`: http://bitmask.rtfd.org

Dependencies
------------------

Bitmask depends on these libraries:

* ``python 2.6`` or ``2.7``
* ``qt4 libraries``
* ``libopenssl``
* ``openvpn``

Python packages are listed in ``pkg/requirements.pip`` and ``pkg/test-requirements.pip``

Getting dependencies under debian
++++++++++++++++++++++++++++++++++

With a Debian based system, to be able to run Bitmask you need to run the following command::

    $ sudo apt-get install git python-dev python-setuptools
    python-virtualenv python-pip python-openssl libsqlite3-dev g++ openvpn
    pyside-tools python-pyside libffi-dev

Installing
-----------

Quick install, from the cheese shop::

  $ sudo pip install leap.bitmask

If you prefer to install from sources::

 $ make
 $ sudo python2 setup.py install


Running
-------

After a successful installation, there should be a launcher called ``bitmask`` somewhere in your path::

  $ bitmask

If you are testing a new provider and do not have a CA certificate chain tied to your SSL certificate, you should execute Bitmask in the following way::

  $ bitmask --danger

But **DO NOT use it on a regular basis**.

**WARNING**: If you use the --danger flag you may be victim to a MITM_ attack without noticing. Use at your own risk.

.. _MITM: http://en.wikipedia.org/wiki/Man-in-the-middle_attack

Hacking
=======

The code is browsable online at::

    https://leap.se/git/?p=bitmask_client.git

If you want to hack on the `develop` branch, the preferred way is to use the `bootstrap_develop.sh` script::

    $ curl https://raw.github.com/leapcode/bitmask_client/develop/pkg/scripts/bootstrap_develop.sh
    $ chmod +x bootstrap_develop.sh

Run the bootstrap script::

    $ ./bootstrap_develop.sh init

This will download all the required repositories and setup the development environment.

Run Bitmask::

    $ ./bootstrap_develop.sh run -dN  # -d for debug and -N for No version check

or::

    $ source bitmask.venv/bin/activate
    $ python bitmask_client/src/leap/bitmask/app.py -dN

**Note**: The `No version check` flag `-N` is required since in the develop branch we have not set (yet) the version number compatible with the current running servers.

Testing
=======

Have a look at ``pkg/test-requirements.pip`` for the tests dependencies.

To run the test suite::

    $ ./run_tests.sh

which the first time should automagically install all the needed dependencies in your virtualenv for you.

License
=======

.. image:: https://raw.github.com/leapcode/bitmask_client/develop/docs/user/gpl.png

Bitmask is released under the terms of the `GNU GPL version 3`_ or later.

.. _`GNU GPL version 3`: http://www.gnu.org/licenses/gpl.txt
