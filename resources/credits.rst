Credits
=======

-  `Credit a New Bank Account`_
-  `Credit an Existing Bank Account`_
-  `Retrieve a Credit`_
-  `Retrieve a Credit (Unstored Bank Account)`_
-  `List All Credits`_
-  `List All Credits for a Bank Account`_


Credit a new bank account
-------------------------

.. code::

    POST /a1/credits


Request
~~~~~~~

``amount``
: *required* **integer**

``description``
: *optional* **string** or `null`

``bank_account``
: *required* **object**
: `Bank Account <./bank_accounts.rst>`_

.. code:: javascript

    {
        "amount": 1716,
        "description": "Math lesson",
        "bank_account": {
            "name": "Gottfried Leibniz",
            "account_number": "3819372930",
            "routing_number": "121042882",
            "type": "checking"
        }
    }

Response
~~~~~~~~

Header
^^^^^^

.. code::

    Status: 201 Created

Body
^^^^

.. code:: javascript


    {
        "amount": 1716,
        "bank_account": {
            "account_number": "xxxxxx2930",
            "name": "Gottfried Leibniz",
            "routing_number": "121042882",
            "fingerprint": "xyz",
            "type": "checking"
        },
        "created_at": "2012-09-26T01:05:39.048250Z",
        "description": "Math lesson",
        "id": "CR7tpfpJezp2McGX43WFqoaK",
        "status": "pending",
        "trace_number": null,
        "uri": "/a1/credits/CR7tpfpJezp2McGX43WFqoaK"
    }



Credit an existing bank account
-------------------------------

.. code::

    POST /a1/bank_accounts/:bank_account_id/credits


Request
~~~~~~~

``amount``
: *required* **integer**

``description``
: *optional* **string** or `null`

.. code:: javascript

    {
        "amount": 1716,
        "description": "Math lesson"
    }

Response
~~~~~~~~

Header
^^^^^^

.. code::

    Status: 201 Created

Body
^^^^

.. code:: javascript


    {
        "amount": 1716,
        "bank_account": {
            "account_number": "xxxxxx2930",
            "created_at": "2012-09-26T01:05:39.455444Z",
            "credits_uri": "/a1/bank_accounts/BA7tRY8SQDOO0tCutsZ8C442/credits/",
            "id": "BA7tRY8SQDOO0tCutsZ8C442",
            "name": "Gottfried Leibniz",
            "routing_number": "121042882",
            "fingerprint": "xyz",
            "type": "checking",
            "uri": "/a1/bank_accounts/BA7tRY8SQDOO0tCutsZ8C442"
        },
        "created_at": "2012-09-26T01:05:39.471760Z",
        "description": "Math lesson",
        "id": "CR7tTvC259MVS1cOHn28cy2m",
        "status": "pending",
        "trace_number": null,
        "uri": "/a1/credits/CR7tTvC259MVS1cOHn28cy2m"
    }



Retrieve a credit
-----------------

.. code::

    GET /a1/credits/:credit_id


Response
~~~~~~~~

Header
^^^^^^

.. code::

    Status: 200 Ok

Body
^^^^

.. code:: javascript


    {
        "amount": 1716,
        "bank_account": {
            "account_number": "xxxxxx2930",
            "created_at": "2012-09-26T01:05:39.874292Z",
            "credits_uri": "/a1/bank_accounts/BA7ulC6zZsOPV51ezmsgHGCS/credits/",
            "id": "BA7ulC6zZsOPV51ezmsgHGCS",
            "name": "Gottfried Leibniz",
            "routing_number": "121042882",
            "fingerprint": "xyz",
            "type": "checking",
            "uri": "/a1/bank_accounts/BA7ulC6zZsOPV51ezmsgHGCS"
        },
        "created_at": "2012-09-26T01:05:39.875901Z",
        "description": null,
        "id": "CR7ul6RkHd0x3gHxKfSn3ivo",
        "status": "pending",
        "trace_number": null,
        "uri": "/a1/credits/CR7ul6RkHd0x3gHxKfSn3ivo"
    }

Retrieve a Credit (Unstored Bank Account)
-----------------------------------------

.. code::

    GET /a1/credits/:credit_id

Response
~~~~~~~~

Header
^^^^^^

.. code::

    Status: 200 Ok

Body
^^^^

.. code:: javascript


    {
        "amount": 1716,
        "bank_account": {
            "account_number": "xxxxxx2930",
            "name": "Gottfried Leibniz",
            "routing_number": "121042882",
            "fingerprint": "xyz",
            "type": "checking"
        },
        "created_at": "2012-09-26T01:05:40.282299Z",
        "description": null,
        "id": "CR7uNm13FsZYahRCMcCUDWQO",
        "status": "pending",
        "trace_number": null,
        "uri": "/a1/credits/CR7uNm13FsZYahRCMcCUDWQO"
    }



List all credits
----------------

.. code::

    GET /a1/credits


Response
~~~~~~~~

Header
^^^^^^

.. code::

    Status: 200 Ok

Body
^^^^

.. code:: javascript


    {
        "items": [
            {
                "amount": 1716,
                "bank_account": {
                    "account_number": "xxxxxx2930",
                    "created_at": "2012-09-26T01:05:40.694863Z",
                    "credits_uri": "/a1/bank_accounts/BA7vgPFGKKvzhxFx8xcFiwJk/credits/",
                    "id": "BA7vgPFGKKvzhxFx8xcFiwJk",
                    "name": "Gottfried Leibniz",
                    "routing_number": "121042882",
                    "fingerprint": "xyz",
                    "type": "checking",
                    "uri": "/a1/bank_accounts/BA7vgPFGKKvzhxFx8xcFiwJk"
                },
                "created_at": "2012-09-26T01:05:40.696339Z",
                "description": null,
                "id": "CR7vglingcQmlsru3ydzKcAO",
                "status": "pending",
                "trace_number": null,
                "uri": "/a1/credits/CR7vglingcQmlsru3ydzKcAO"
            },
            {
                "amount": 1716,
                "bank_account": {
                    "account_number": "xxxxxx2930",
                    "created_at": "2012-09-26T01:05:40.706645Z",
                    "credits_uri": "/a1/bank_accounts/BA7vhIcSRabWuw67ZQt34n7Y/credits/",
                    "id": "BA7vhIcSRabWuw67ZQt34n7Y",
                    "name": "Gottfried Leibniz",
                    "routing_number": "121042882",
                    "fingerprint": "xyz",
                    "type": "checking",
                    "uri": "/a1/bank_accounts/BA7vhIcSRabWuw67ZQt34n7Y"
                },
                "created_at": "2012-09-26T01:05:40.707124Z",
                "description": null,
                "id": "CR7vhF70LzK8YRfGXraqXuoG",
                "status": "pending",
                "trace_number": null,
                "uri": "/a1/credits/CR7vhF70LzK8YRfGXraqXuoG"
            },
            {
                "amount": 1716,
                "bank_account": {
                    "account_number": "xxxxxx2930",
                    "created_at": "2012-09-26T01:05:40.713831Z",
                    "credits_uri": "/a1/bank_accounts/BA7vid5DNb8AX9rD2Jehni0q/credits/",
                    "id": "BA7vid5DNb8AX9rD2Jehni0q",
                    "name": "Gottfried Leibniz",
                    "routing_number": "121042882",
                    "fingerprint": "xyz",
                    "type": "checking",
                    "uri": "/a1/bank_accounts/BA7vid5DNb8AX9rD2Jehni0q"
                },
                "created_at": "2012-09-26T01:05:40.714570Z",
                "description": null,
                "id": "CR7viaeJ3HkaQg9cUNjiLW7o",
                "status": "pending",
                "trace_number": null,
                "uri": "/a1/credits/CR7viaeJ3HkaQg9cUNjiLW7o"
            }
        ]
    }



List all credits for a bank account
-----------------------------------

.. code::

    GET /a1/bank_accounts/:bank_account_id/credits


Response
~~~~~~~~

Header
^^^^^^

.. code::

    Status: 200 Ok

Body
^^^^

.. code:: javascript


    {
        "items": [
            {
                "amount": 221970,
                "bank_account": {
                    "account_number": "xxxxxx2930",
                    "created_at": "2012-09-26T01:05:41.115769Z",
                    "credits_uri": "/a1/bank_accounts/BA7vJLojGjlpqpAtrTsZPeVY/credits/",
                    "id": "BA7vJLojGjlpqpAtrTsZPeVY",
                    "name": "Gottfried Leibniz",
                    "routing_number": "121042882",
                    "fingerprint": "xyz",
                    "type": "checking",
                    "uri": "/a1/bank_accounts/BA7vJLojGjlpqpAtrTsZPeVY"
                },
                "created_at": "2012-09-26T01:05:41.132034Z",
                "description": null,
                "id": "CR7vLhh8XvtzUuMJBW53DXce",
                "status": "pending",
                "trace_number": null,
                "uri": "/a1/credits/CR7vLhh8XvtzUuMJBW53DXce"
            },
            {
                "amount": 4281906,
                "bank_account": {
                    "account_number": "xxxxxx2930",
                    "created_at": "2012-09-26T01:05:41.115769Z",
                    "credits_uri": "/a1/bank_accounts/BA7vJLojGjlpqpAtrTsZPeVY/credits/",
                    "id": "BA7vJLojGjlpqpAtrTsZPeVY",
                    "name": "Gottfried Leibniz",
                    "routing_number": "121042882",
                    "fingerprint": "xyz",
                    "type": "checking",
                    "uri": "/a1/bank_accounts/BA7vJLojGjlpqpAtrTsZPeVY"
                },
                "created_at": "2012-09-26T01:05:41.142644Z",
                "description": null,
                "id": "CR7vM5mxthVqq1HKl3hFT90u",
                "status": "pending",
                "trace_number": null,
                "uri": "/a1/credits/CR7vM5mxthVqq1HKl3hFT90u"
            },
            {
                "amount": 1300,
                "bank_account": {
                    "account_number": "xxxxxx2930",
                    "created_at": "2012-09-26T01:05:41.115769Z",
                    "credits_uri": "/a1/bank_accounts/BA7vJLojGjlpqpAtrTsZPeVY/credits/",
                    "id": "BA7vJLojGjlpqpAtrTsZPeVY",
                    "name": "Gottfried Leibniz",
                    "routing_number": "121042882",
                    "fingerprint": "xyz",
                    "type": "checking",
                    "uri": "/a1/bank_accounts/BA7vJLojGjlpqpAtrTsZPeVY"
                },
                "created_at": "2012-09-26T01:05:41.151774Z",
                "description": null,
                "id": "CR7vMIyVhoWcTwAsQRKZdwjU",
                "status": "pending",
                "trace_number": null,
                "uri": "/a1/credits/CR7vMIyVhoWcTwAsQRKZdwjU"
            }
        ]
    }