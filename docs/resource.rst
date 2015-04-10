Resource
########

.. _resource-class:

.. automodule:: cliquet.resource
    :members:


Custom record ids
=================

By default, records ids are `UUID4 <http://en.wikipedia.org/wiki/Universally_unique_identifier>_`.

A custom record id generator can be set globally in :ref:`configuration`,
or at the resource level:

.. code-block :: python

    from cliquet import resource
    from cliquet import utils
    from cliquet.storage import generators


    class MsecId(generators.Generator):
        def __call__(self):
            return '%s' % utils.msec_time()


    @resource.crud()
    class Mushroom(resource.BaseResource):
        id_generator = MsecId()


Generators objects
::::::::::::::::::

.. automodule:: cliquet.storage.generators
    :members:
