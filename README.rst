Google Cloud Python Client
==========================

    Python idiomatic client for Google Cloud Platform services.

|build| |coverage|
------------------

-  `Homepage <https://googlecloudplatform.github.io/gcloud-python/>`__

This client supports the following Google Cloud Platform services:

-  `Google Cloud
   Datastore <https://cloud.google.com/products/cloud-datastore/>`__
-  `Google Cloud
   Storage <https://cloud.google.com/products/cloud-storage/>`__

If you need support for other Google APIs, check out the `Google APIs
Python Client
library <https://github.com/google/google-api-python-client>`__.

Quickstart
----------

::

    $ pip install gcloud

Google Cloud Datastore
----------------------

`Google Cloud Datastore <https://developers.google.com/datastore/>`__ is
a fully managed, schemaless database for storing non-relational data.
Cloud Datastore automatically scales with your users and supports ACID
transactions, high availability of reads and writes, strong consistency
for reads and ancestor queries, and eventual consistency for all other
queries.

See the `Google Cloud Datastore
docs <https://developers.google.com/datastore/docs/activate>`__ for more
details on how to activate Cloud Datastore for your project.

See `the gcloud-python API
documentation <https://googlecloudplatform.github.io/gcloud-python/datastore-api.html>`__
to learn how to interact with the Cloud Datastore using this Client
Library.

.. code:: python

    from gcloud import datastore
    dataset = datastore.get_dataset('dataset-id-here',
                                    'long-email@googleapis.com',
                                    '/path/to/private.key')
    # Then do other things...
    query = dataset.query().kind('EntityKind')
    entity = dataset.entity('EntityKind')

Google Cloud Storage
--------------------

`Google Cloud Storage <https://developers.google.com/storage/>`__ allows
you to store data on Google infrastructure with very high reliability,
performance and availability, and can be used to distribute large data
objects to users via direct download.

You need to create a Google Cloud Storage bucket to use this client
library. Follow the steps on the `Google Cloud Storage
docs <https://developers.google.com/storage/docs/cloud-console#_creatingbuckets>`__
to learn how to create a bucket.

See `the gcloud-python API
documentation <https://googlecloudplatform.github.io/gcloud-python/storage-api.html>`__
to learn how to connect to the Cloud Storage using this Client Library.

.. code:: python

    import gcloud.storage
    bucket = gcloud.storage.get_bucket('bucket-id-here',
                                        'long-email@googleapis.com',
                                        '/path/to/private.key')
    # Then do other things...
    key = bucket.get_key('/remote/path/to/file.txt')
    print key.get_contents_as_string()
    key.set_contents_from_string('New contents!')
    bucket.upload_file('/remote/path/storage.txt', '/local/path.txt')

Contributing
------------

Contributions to this library are always welcome and highly encouraged.

See `CONTRIBUTING <CONTRIBUTING.rst>`__ for more information on how to
get started.

Supported Python Versions
-------------------------

We support:

-  `Python 2.6 <https://docs.python.org/2.6/>`__
-  `Python 2.7 <https://docs.python.org/2.7/>`__

We plan to support:

-  `Python 3.3 <https://docs.python.org/3.3/>`__
-  `Python 3.4 <https://docs.python.org/3.4/>`__

Supported versions can be found in our ``tox.ini``
`config <https://github.com/GoogleCloudPlatform/gcloud-python/blob/master/tox.ini>`__.

We explicitly decided not to support
`Python 2.5 <https://docs.python.org/2.5/>`__ due to
`decreased usage <https://caremad.io/2013/10/a-look-at-pypi-downloads/>`__ and
lack of continuous integration
`support <http://blog.travis-ci.com/2013-11-18-upcoming-build-environment-updates/>`__.

We also explicitly decided to support Python 3 beginning with version 3.3.
Reasons for this include:

-  Encouraging use of newest versions of Python 3
-  Taking the lead of prominent open-source
   `projects <http://flask.pocoo.org/docs/0.10/python3/>`__
-  Unicode literal `support <https://www.python.org/dev/peps/pep-0414>`__ which
   allows for a cleaner codebase that works in both Python 2 and Python 3.

License
-------

Apache 2.0 - See `LICENSE <LICENSE>`__ for more information.

.. |build| image:: https://travis-ci.org/GoogleCloudPlatform/gcloud-python.svg?branch=master
    :target: https://travis-ci.org/GoogleCloudPlatform/gcloud-python
.. |coverage| image:: https://coveralls.io/repos/GoogleCloudPlatform/gcloud-python/badge.png?branch=master
    :target: https://coveralls.io/r/GoogleCloudPlatform/gcloud-python?branch=master
