### ripple-python
---
https://github.com/miracle2k/ripple-python/

```py
// tests/test_datastructures.py
from decimal import Decimal
from pytest import raises
from ripple.datastructures import Amount

def test_amount():
  assert Amount(10).currency == 'XRP'
  assert Amount(10).issuer == None
  assert Amount(10).value == Decimal('0.00001')
  

```

```json
// tests/tx/account_root_node_without_fields.json
{
  "Paths": [
    [
      {
        "type": 1,
        "type_hex": "0000",
        "account": "xxx"
      },
    ]
  ]
}
```

```
```


