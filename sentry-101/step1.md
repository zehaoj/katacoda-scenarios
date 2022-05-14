
## Install
Sentry captures data by using an SDK within your application’s runtime. First, we need to install the Python SDK using pip:
`pip install --upgrade sentry-sdk`{{execute}}

`test.py`{{open}}

```
import sentry_sdk

sentry_sdk.init(
    "https://examplePublicKey@o0.ingest.sentry.io/0",

    # Set traces_sample_rate to 1.0 to capture 100%
    # of transactions for performance monitoring.
    # We recommend adjusting this value in production.
    traces_sample_rate=1.0,
)
```{{copy}}