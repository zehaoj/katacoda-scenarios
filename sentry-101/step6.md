## Add Context
Custom contexts allow you to attach arbitrary data to an event. The best practice to attach custom data is via structured contexts. A context must always be a dictionary or map, and its values can be arbitrary.

Then, use `set_context` and give the context a unique name:

```
import sentry_sdk

sentry_sdk.set_context("character", {
    "name": "Mighty Fighter",
    "age": 19,
    "attack_type": "melee"
})
```

There are no restrictions on context name. In the context object, all keys are allowed except for `type`, which is used internally.

## Set Transaction Name

The current transaction name is used to group transactions in our Performance product, as well as annotate error events with their point of failure.

To override the name of the currently running transaction:

```
from sentry_sdk import configure_scope

with configure_scope() as scope:
    scope.transaction.name = "UserListView"
```

## Customize Tags
Tags are key/value string pairs that are both indexed and searchable. Define the tag:

```
from sentry_sdk import set_tag

set_tag("page.locale", "de-at")
```
