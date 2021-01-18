Widgets
=======

Product
-------

Add an HTML element on your product page to display the Postpay payment options.

The element attributes determine which component displays:

.. code-block:: html

    <div class="postpay-widget"
         data-type="product"
         data-amount="{amount}"
         data-currency="{currency}"
         data-num-instalments="{numInstalments}"
         data-locale="en">
    </div>

.. list-table::
    :header-rows: 1
    :widths: 25 20 55

    * - Attribute
      - Type
      - Description
    * - data-amount
      - Integer❗
      - Product unit price expressed in the smallest unit of currency.
    * - data-currency
      - String❗
      - `ISO 4217 <https://en.wikipedia.org/wiki/ISO_4217>`__ currency code.
    * - data-num-instalments
      - Integer
      - The number of instalments. Postpay sets an **optimal number of instalments** by default.
    * - locale
      - String
      - The locale code, options are ``en`` (English) and ``ar`` (Arabic). Default: the value defined in the [initialization](quickstart).

.. raw:: html

    <embed>
      <fieldset>
        <legend>&lt;demo/&gt;</legend>
        <div class="postpay-widget"
             data-type="product"
             data-amount="24000"
             data-currency="AED"
             data-num-instalments="4">
        </div>
      </fieldset>
    </embed>

Cart
----

Add an HTML element on your cart page to display the Postpay payment options.

The element attributes determine which component displays:

.. code-block:: html

    <div class="postpay-widget"
         data-type="cart"
         data-amount="{amount}"
         data-currency="{currency}"
         data-num-instalments="{numInstalments}"
         data-locale="en">
    </div>

.. list-table::
    :header-rows: 1
    :widths: 25 20 55

    * - Attribute
      - Type
      - Description
    * - data-amount
      - Integer❗
      - Cart total amount expressed in the smallest unit of currency.
    * - data-currency
      - String❗
      - `ISO 4217 <https://en.wikipedia.org/wiki/ISO_4217>`__ currency code.
    * - data-num-instalments
      - Integer
      - The number of instalments. Postpay sets an **optimal number of instalments** by default.
    * - locale
      - String
      - The locale code, options are ``en`` (English) and ``ar`` (Arabic). Default: the value defined in the [initialization](quickstart).

.. raw:: html

    <embed>
      <fieldset>
        <legend>&lt;demo/&gt;</legend>
        <div class="postpay-widget"
             data-type="cart"
             data-amount="48000"
             data-currency="AED"
             data-num-instalments="4">
        </div>
      </fieldset>
    </embed>

Payment summary
---------------

This widget is commonly used to display the payment summary on the payment method selection.

Set ``data-hide-if-invalid`` to disable Postpay payment method in case it is not available for the configured attributes, e.g. the total amount exceeds the maximum allowed.

.. code-block:: html

    <div class="postpay-widget"
         data-type="payment-summary"
         data-amount="{amount}"
         data-currency="{currency}"
         data-num-instalments="{numInstalments}"
         data-country="{country}"
         data-hide-if-invalid="{selector}"
         data-locale="en">
    </div>

.. list-table::
    :header-rows: 1
    :widths: 25 20 55

    * - Attribute
      - Type
      - Description
    * - data-amount
      - Integer❗
      - Cart total amount expressed in the smallest unit of currency.
    * - data-currency
      - String❗
      - `ISO 4217 <https://en.wikipedia.org/wiki/ISO_4217>`__ currency code.
    * - data-num-instalments
      - Integer
      - The number of instalments. Postpay sets an **optimal number of instalments** by default. Set ``1`` for **Pay Now** payment option.
    * - data-country
      - String
      - `ISO 3166 alpha-2  <https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2>`__ country code for the shipping address.
    * - data-hide-if-invalid
      - String
      - CSS selector to hide the HTML elements if Postpay payment method is not available for this cart.
    * - locale
      - String
      - The locale code, options are ``en`` (English) and ``ar`` (Arabic). Default: the value defined in the [initialization](quickstart).

.. raw:: html

    <embed>
      <fieldset>
        <legend>&lt;demo/&gt;</legend>

        <ul class="payment-method">
          <li>
            <input type="radio" name="payment-method">
            <label>Cash on delivery</label>
          </li>

          <li>
            <input type="radio" name="payment-method">
            <label>Credit or Debit Card <img src="_static/images/postpay-pay-now.png"></label>

            <div class="postpay-widget"
                 data-type="payment-summary"
                 data-amount="48000"
                 data-currency="AED"
                 data-num-instalments="1">
            </div>
          </li>

          <li>
            <input type="radio" name="payment-method" checked="checked">
            <label>Instalments with Postpay <img src="_static/images/logo.png"></label>

            <div class="postpay-widget"
                 data-type="payment-summary"
                 data-amount="48000"
                 data-currency="AED"
                 data-num-instalments="4">
            </div>
          </li>
        </ul>
      </fieldset>
    </embed>


Refresh
-------

The price displayed on your checkout pages may change due to product variants, currency, etc.

To keep messaging updated, implement this refresh function into your cart change callback function:

.. code-block:: html

    <script>
      postpay.ui.refresh();
    </script>
