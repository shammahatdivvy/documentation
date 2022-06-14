---
id: how-to-define-activity-parameters-in-python
title: How to define Activity Parameters in Python
sidebar_label: Activity Parameters
description: Activities can support many custom parameters.
tags:
  - developer-guide
  - python
---

Activity parameters are the function parameters of the function decorated with
`@activity.defn`. These can be any data type Temporal can convert including
`dataclass`es. Technically this can be multiple parameters, but Temporal
strongly encourages a single `dataclass` parameter containing all input fields.
For example:

```python
@dataclass
class MyParams:
    my_int_param: int
    my_str_param: str


@activity.defn
async def my_activity(params: MyParams) -> None:
    # Do stuff
    ...
```