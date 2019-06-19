---
title: strings.replace() function
description: >
  The strings.replace() function replaces the first `i` non-overlapping instances
  of a substring with a specified replacement.
menu:
  v2_0_ref:
    name: strings.replace
    parent: Strings
weight: 301
related:
  - /v2.0/reference/flux/functions/strings/replaceall
---

The `strings.replace()` function replaces the first `i` non-overlapping instances of a substring with a specified replacement.

_**Output data type:** String_

```js
import "strings"

strings.replace(v: "oink oink oink", t: "oink", u: "moo", i: 2)

// returns "moo moo oink"
```

## Parameters

### v
The string value to search.

_**Data type:** String_

### t
The string value to replace.

_**Data type:** String_

### u
The string value to replace `i` instances of `t`.

_**Data type:** String_

### i
The number of non-overlapping `t` matches to replace.

_**Data type:** Integer_

## Examples

###### Replace a specific number of string matches
```js
import "strings"

data
  |> map(fn: (r) => ({
      content: strings.replace(v: r.content, t: "he", u: "her", i: 3)
    })
  )
```