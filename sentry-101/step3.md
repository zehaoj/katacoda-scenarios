# Python SDK Setup
## Install
Sentry captures data by using an SDK within your application’s runtime. After setting up on the Sentry side, we need to install the Python SDK using pip:
`pip install --upgrade sentry-sdk`{{execute}}


## Configure
Configuration should happen as early as possible in your application's lifecycle. Once this is done, Sentry's Python SDK captures all unhandled exceptions and transactions.

Open `test.py`{{open}} and copy the following lines of code to it and replace the string with the url you got from last step.

```
import sentry_sdk

sentry_sdk.init(
    "**REPLACE_THIS_WITH_THE_URL_FROM_LAST_STEP**",

    # Set traces_sample_rate to 1.0 to capture 100%
    # of transactions for performance monitoring.
    # We recommend adjusting this value in production.
    traces_sample_rate=1.0,
)
```


## Verify
This snippet includes an intentional error, so you can test that everything is working as soon as you set it up. Copy this in the `test.py`{{open}} under the code from configuration:

`division_by_zero = 1 / 0`{{copy}}

and run

`python3 test.py`{{execute}}

And if everything was done correctly, you should see this issue warning in the Sentry console under the project you created before.

![](https://tva1.sinaimg.cn/large/e6c9d24egy1h28i02ys7bj21aa0kawgm.jpg)