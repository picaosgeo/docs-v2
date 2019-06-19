---
title: strings.containsAny() function
description: >
  The strings.containsAny() function reports whether a specified string contains
  any characters from from another string.
menu:
  v2_0_ref:
    name: strings.containsAny
    parent: Strings
weight: 301
related:
  - /v2.0/reference/flux/functions/strings/containsstr
---

The `strings.containsAny()` function reports whether a specified string contains
characters from another string.

_**Output data type:** Boolean_

```js
import "strings"

strings.containsAny(v: "abc", chars: "and")

// returns true
```

## Parameters

### v
The string value to search.

_**Data type:** String_

### chars
Characters to search for.

_**Data type:** String_

## Examples

###### Report if a string contains specific characters
```js
import "strings"

data
  |> map(fn: (r) => ({
      _value: strings.containsAny(v: r.price, chars: "£$¢")
    })
  )
```