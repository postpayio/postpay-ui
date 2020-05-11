Quickstart
==========

Add the Postpai SDK by including the following script in the ``<body>`` section:

.. code-block:: html

    <script>
      window.postpayAsyncInit = function() {
        postpay.init({
          merchantId: '{merchantId}',
          sandbox: false,
          theme: 'light'
        });
      };
    </script>

    <script async src="https://cdn.postpay.io/v1/js/postpay.js"></script>

.. list-table::
    :header-rows: 1
    :widths: 25 20 55

    * - Option
      - Type
      - Description
    * - merchantId
      - String❗
      - Merchant ID.
    * - sandbox
      - Boolean
      - Set to ``true`` for testing evironment. Default: ``false``.
    * - theme
      - String
      - The client handler, options are ``light`` and ``dark``. Default: ``light``.

A trailing exclamation mark❗is used to denote a field that uses a Non‐Null type. By default, all types are nullable.
