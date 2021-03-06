## Modifier group - Create

Create modifier group.

> Request (POS -> weorder)

```
HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/1/modifier-groups
```

```json
{
    "modifierGroupNo": 11,
    "name": "Additional ingredients for pizza",
    "type": "ANY",
    "description": "Add additional portion of:",
    "modifiers": [22, 23, 24]
}
```

### HTTP Request

`HTTP/1.1 PUT https://api.weorder.com/pos/v1/merchant-groups/{merchantGroupNo}/modifier-groups`

`Content-Type: application/json`

### Request Parameters

Parameter | Data type | Required? | Format | Description
--------- | --------- | --------- | ------ | -----------
modifierGroupNo | integer | true | \d+ | modifier group number
name | string | true | | modifier group name
type | string | false | ONE / ANY | type (how many modifiers can be chosen)
description | string | false | | modifier group description
modifiers | array | false | array of integer | list of related modifiers (modifierNo). You can use this parameter if you want to set/update relations between modifier group and its modifiers. The order of passed modifiers is important and will be used for sorting.

Supported types |
--------------- |
ONE |
ANY |

> Response: no content

### HTTP Response (success)

`HTTP/1.1 201`
