## Breadcrumbs
Sentry uses breadcrumbs to create a trail of events that happened prior to an issue. These events are very similar to traditional logs, but can record more rich structured data.

### Manual Breadcrumbs
You can manually add breadcrumbs whenever something interesting happens. For example, you might manually record a breadcrumb if the user authenticates or another state change occurs.

Manually record a breadcrumb:

```
from sentry_sdk import add_breadcrumb

add_breadcrumb(
    category='auth',
    message='Authenticated user %s' % user.email,
    level='info',
)
```

The available breadcrumb keys are `type`, `category`, `message`, `level`, `timestamp` and `data`, which is the place to put any additional information you'd like the breadcrumb to include.

### Customize Breadcrumbs
`before_breadcrumb` hook is passed an already assembled breadcrumb and, in some SDKs, an optional hint. The function can modify the breadcrumb or decide to discard it entirely by returning null:

```

import sentry_sdk

def before_breadcrumb(crumb, hint):
    if crumb['category'] == 'a.spammy.Logger':
        return None
    return crumb

sentry_sdk.init(before_breadcrumb=before_breadcrumb)
```