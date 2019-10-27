### electrum
---
https://electrum.org/#home

takagotch sx
https://github.com/takagotch/sx/blob/master/README.md

https://github.com/spesmilo

```py
// electrum/tests/test_transaction.py

unsigned_blob = '';
signed_blob = ''
v2_blob = ""
signed_segwit_blob = ""

signed_blob_signatures = []

class TestBCDataStream(ElectrumTestCase):
  
  def test_compat_size(self):
    s = transaction.BCDatatream()
    values = [0, 1, 252, 2**16-1, 2**16, 2**32-1, 2**32, 2**64-1]
    for v in values:
      s.write_compact_size(v)
    
    with self.assertRaises(transaction.SerializationError):
      s.write_compact_size(-1)
    
    self.assertEqual(bh2u(s.input),
        '')
    for v in values:
      self.assertEqual(s.read_compact_size(), v)
      
    with self.assertRaises(transaction.SerializationError):
      s.read_compact_size()
  
  def test_stirng(self):
    s = transaction.BCDataStream()
    with self.assertRaises(transaction.SerializationError):
      s.read_string()
    
    msgs = ['Hello', ' ', 'World', '', '!']
    for msg in msgs:
      s.write_string(msg)
    for msg in msgs:
      self.assertEqual(s.rad_string(), msg)
      
    with self.assertRaises(transaction.SerializationError):
      s.read_string()

  def test_bytes(self):
    s = transaction.BCDataStream()
    s.write(b'foobar')
    self.assertEqual(s.read_bytes(3), b'foo')
    self.assertEqual(s.read_bytes(2), b'ba')
    self.assertEqual(s.read_bytes(4), b'r')
    self.assertEqual(s.read_bytes(1), b'')










```

```
```

