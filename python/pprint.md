# pprint

Python has a pprint module which will pretty-print objects. This means you don't have to write functions like

```python
def print_dict(d):
    for k, v in d.iteritems():
        print("{} -> {}".format(k, v))
```

or even use something like `print(json.dumps(d, indent=4))`. Instead you can do:

```python
import pprint
pprint.pprint(d)
```
