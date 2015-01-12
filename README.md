PyFanout
========
Author: Justin Karneges <justin@fanout.io>

Fanout.io library for Python.

Requirements
------------

* PyJWT
* pubcontrol

Install
-------

You can install from PyPi:

    sudo pip install fanout

Or from this repository:

    sudo python setup.py install

Sample usage
------------

```python
import fanout

def callback(result, message):
    if result:
        print('Publish successful')
    else:
        print('Publish failed with message: ' + message)

fanout.realm = 'my-realm-id'
fanout.key = 'my-realm-key'

fanout.publish('some-channel', 'hello')
fanout.publish('some-channel', 'async hello', blocking=False,
        callback=callback)
```
