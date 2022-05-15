# Usage

## Capturing Errors & Messages
The reporting of an event is called *capturing*. When an event is captured, it’s sent to Sentry. 

The most common form of capturing is to capture errors. In general, if you have something that looks like an exception, it can be captured.


```
from sentry_sdk import capture_exception

try:
    a_potentially_failing_function()
except Exception as e:
    # Alternatively the argument can be omitted
    capture_exception(e)
    
a_potentially_failing_function():
	print(int('e'))
```


```
from sentry_sdk import capture_message

capture_message('Something went wrong')
```