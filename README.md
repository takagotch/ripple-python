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
  assert Amount(Decimal('10')).value == Decimal('10')
  assert Amount('10.0').value == Decimal('10')
  assert Amount('10').value == Decimal('0.00001')
  assert Amount('10.0').__json() == 100000000
  
  a = Amount(15)
  a.value = 10
  assert a.data == 100000000
  a = Amount({'value': '10', 'currency': 'USD'})
  a.value = 15
  assert a.data['value'] == '15'
  
  assert (Amount(10) + Amount(15)).value == Decimal('0.000025')
  assert (Amount({'value': '10', 'currency': 'USD'}) - '2').value == 8
  
  amount = Amount({'value': '10', 'currency': 'USD'})
  assert not ('issuer' in amount)
  amount['issuer'] = 'foo'
  assert amount.issuer == 'foo'
  

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


