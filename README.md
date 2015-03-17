CryptsyPythonV2
===============

Python Library for Cryptsy's V2 API that is Python 3.4.2 compatible


Requirements
============
* Source code Tested in Python 2.7, change to accomodate Python 3.4.
* requests lib. (http://docs.python-requests.org/en/latest/)
* Using anaconda distribution with Python 3.4.2 for development. It is free to download and install.

Examples
========
Print Last Hours Worth of OHLC
```python
from Cryptsy import Cryptsy
from pprint import pprint
import time

c = Cryptsy("", "")
c._getkey("cryptsy.key")
ohlc = c.market_ohlc(132, start=0, stop=time.time(), interval="minute", limit=60)
pprint(ohlc)
```


List Currencies
```python
from Cryptsy import Cryptsy
from pprint import pprint

c = Cryptsy("", "")
c._getkey("cryptsy.key")
currencies = c.currencies()
pprint(currencies)
```


Account Balances
```python
from Cryptsy import Cryptsy
from pprint import pprint
c = Cryptsy()
c._getkey("cryptsy.key")
balances = c.balances()
pprint(balances)
```


Market Orderbook (Open/Pending Orders)
```python
from Cryptsy import Cryptsy
from pprint import pprint
c = Cryptsy()
c._getkey("cryptsy.key")
market_orderbook = c.market_orderbook(1)
pprint(market_orderbook)


Create Converter Quote with 2% fee.
```python
from Cryptsy import Cryptsy
from pprint import pprint
c = Cryptsy()
c._getkey("cryptsy.key")
quote = c.convert_create(3, 132, sendingamount=1, tradekey="", feepercent=2)
pprint(quote)
```
