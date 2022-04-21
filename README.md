# Email-varication-Api
There are many website ehcih provide API's for Email varication. This website is one of them... it priovide 1,000 email varifaction for free, just signup and get 1,000 free email varification...

### website URL:
https://main.whoisxmlapi.com/

### YouTube Video Link:
https://youtu.be/4-JkmUGCV1w




## For Detail and Usage:

python-email-verifier
===================

The simplest possible way to verify an email address in Python.

Meta
----

- Author: WHOIS API, Inc.
- Email: support@whoisxmlapi.com
- Site: https://emailverification.whoisxmlapi.com/


Prerequisites
-------------

To use this library, you'll need to create a free Email Verification API account:
https://emailverification.whoisxmlapi.com/

If you haven't done this yet, please do so now.


Documentation
-------------

Documentation available `here <https://emailverification.whoisxmlapi.com/docs>`_.

Installation
------------

To install ``email-verifier`` using `pypi <https://pypi.org/>`_, simply run:

.. code-block:: console

    $ pip install email-verifier

In the root of your project directory.


Usage
-----

Once you have `email-verified` installed, you can use it to easily verify any
email address.

### Now copy the code and enjoy it :apple:

.. code-block:: python

    from emailverifier import Client
    from emailverifier import exceptions

    client = Client('Your-api-key')

    try:
        data = client.get("support@whoisxmlapi.com")
    except exceptions.HttpException:
        # If you get here, it means service returned HTTP error code
        pass
    except exceptions.GeneralException:
        # If you get here, it means you cannot connect to the service
        pass
    except exceptions.UndefinedVariableException:
        # If you get here, it means you forgot to specify the API key
        pass
    except exceptions.InvalidArgumentException:
        # If you get here, it means you specified invalid argument
        # (options should be a dictionary)
        pass
    except:
        pass
        # Something else happened related. Maybe you hit CTRL-C
        # while the program was running, the kernel is killing your process, or
        # something else all together.

    print(data)

    # Use data.json_string to get raw data in JSON.
    # You can access any response field as a class property
    # by converting field name from "camelCase" to "snake_case"
    print("Email address: " + data.email_address)
    print("Format: " + str(data.format_check))
    print("DNS: " + str(data.dns_check))
    print("SMTP: " + str(data.smtp_check))
    print("Catch all: " + str(data.catch_all_check))
    print("Disposable: " + str(data.disposable_check))
    print("Free: " + str(data.free_check))
    print("Last audit date: " + str(data.audit.audit_updated_date))

Here's the sort of data you might get back when performing a email verification
request:

.. code-block:: json

    {
      "emailAddress": "support@whoisxmlapi.com",
      "formatCheck": "true",
      "smtpCheck": "true",
      "dnsCheck": "true",
      "freeCheck": "false",
      "disposableCheck": "false",
      "catchAllCheck": "true",
      "mxRecords": [
        "ALT1.ASPMX.L.GOOGLE.com",
        "ALT2.ASPMX.L.GOOGLE.com",
        "ASPMX.L.GOOGLE.com",
        "ASPMX2.GOOGLEMAIL.com",
        "ASPMX3.GOOGLEMAIL.com",
        "mx.yandex.net"
      ],
      "audit": {
        "auditCreatedDate": "2018-04-19 18:12:45.000 UTC",
        "auditUpdatedDate": "2018-04-19 18:12:45.000 UTC"
      }
    }









