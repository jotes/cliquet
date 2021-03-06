##################################
Utility endpoints for OPS and Devs
##################################

GET /
=====

The returned value is a JSON mapping containing:

- ``hello``: the name of the service (e.g. ``"reading list"``)
- ``version``: complete version (``"X.Y.Z"``)
- ``url``: absolute URI (without a trailing slash) of the API (*can be used by client to build URIs*)
- ``eos``: date of end of support in ISO 8601 format (``"yyyy-mm-dd"``, undefined if unknown)
- ``documentation``: The url to the service documentation. (this document!)


GET /__heartbeat__
==================

Return the status of each service the your application depends on. The
returned value is a JSON mapping containing:

- ``database`` true if operational

Return ``200`` if the connection with each service is working properly
and ``503`` if something doesn't work.
