## Performance Monitoring
With performance monitoring, Sentry tracks your software performance, measuring metrics like throughput and latency, and displaying the impact of errors across multiple systems.

Copy this code snippet to the `test.py`{{open}} file below the `sentry_sdk.init()` you defined earlier:

```
from sentry_sdk import start_transaction

cc = 0
while cc < 100:
	item = cc
	with start_transaction(op="task", name="test"):
		item = item ^ item
		cc += 1   
```
and run `python3 test.py`{{excecute}}. 

You could check the performance details like time breakdown, frequency, cumulative duration, etc in the [Sentry](https://sentry.io) console as well.

![](https://tva1.sinaimg.cn/large/e6c9d24egy1h29cpry7a7j20wv0u0tch.jpg)