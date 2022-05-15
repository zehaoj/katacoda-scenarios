## Capturing Errors & Messages
The reporting of an event is called *capturing*. When an event is captured, it’s sent to Sentry. 

The most common form of capturing is to capture errors. In general, if you have something that looks like an exception, it can be captured.

Copy this code snippet in the `test.py`{{open}} file below the `sentry_sdk.init()` you defined earlier:

```
from sentry_sdk import capture_exception

try:
	# This would raise error 
    print(int('e'))
except Exception as e:
    # Alternatively the argument can be omitted
    capture_exception(e)
```
and run `python3 test.py`{{excecute}}. 

You could see a `ValueError` raised in the sentry.io console.

![](https://tva1.sinaimg.cn/large/e6c9d24egy1h29baz0c2kj218804gq3b.jpg)

Another common operation is to capture a bare message. A message is textual information that should be sent to Sentry. Typically messages are not emitted, but they can be useful for some teams. 


```
from sentry_sdk import capture_message

capture_message('Something went wrong')
```