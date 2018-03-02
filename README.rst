.. -*- mode: rst -*-


pybitflyer
==========

``pybitflyer``　は bitFlyerの REST APIのライブラリ。一部API変更があるようで。

Install
-------
 pip　でどうぞ。

.. code::

  $ pip install git+https://github.com/haniokasai/pybitflyer.git

必要な要素は自動でインストールされない気がするので、察してください。

Usage
-----

.. code:: python

  import pybitflyer
  api = pybitflyer.API(api_key="xxx...", api_secret="yyy...")

 HTTP Public APIを使うならば、 API Key と API Secret　は省略可能。

.. code:: python

  import pybitflyer
  api = pybitflyer.API()

例
-------

Order Book
~~~~~~~~~~

.. code:: python

  api.board(product_code="BTC_JPY")

Ticker
~~~~~~

.. code:: python

  api.ticker(product_code="BTC_JPY")

注文作成
~~~~~~~~~~~~~~~~

APIキーとシークレットを設定してください。

.. code:: python

  api.sendchildorder(product_code="BTC_JPY",
                     child_order_type="MARKET",
                     side="SELL",
                     size=0.001,
                     minute_to_expire=10000,
                     time_in_force="GTC"
                     )

詳細
~~~~~~~~~~~

詳しいことはこれを読んで察してください: https://lightning.bitflyer.jp/docs?lang=en

Author
------

@haniokasai (<htek@haniokasai.com>)
@yag_ays (<yanagi.ayase@gmail.com>)
