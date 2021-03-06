OpenId
======

OpenId_ support is simpler to implement than OAuth_. Google and Yahoo
providers are supported by default, others are supported by POST method
providing endpoint URL.

OpenId_ backends can store extra data in UserSocialAuth.extra_data field
by defining a set of values names to retrieve from any of the used schemas,
pettributeExchange and SimpleRegistration. As their keywords differ we need
two settings.

Settings is per backend, so we have two possible values for each one. Name
is dynamically checked using uppercase backend name as prefix::

    <uppercase backend name>_SREG_EXTRA_DATA
    <uppercase backend name>_AX_EXTRA_DATA

Example::

    GOOGLE_SREG_EXTRA_DATA = [(..., ...)]
    GOOGLE_AX_EXTRA_DATA = [(..., ...)]

Settings must be a list of tuples mapping value name in response and value
alias used to store.

.. _OpenId: http://openid.net/
.. _OAuth: http://oauth.net/
