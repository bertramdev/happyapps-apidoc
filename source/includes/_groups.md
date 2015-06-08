# Groups

Groups are a useful means to organize a set of checks. An example might be 3 web servers grouped under a web balancer. Or 2 mysql servers tied together as masters. This can be useful in setting up a hierarchy of the application infrastructure and help to properly create an availability discernment for you and your customers.

## Get All Groups

```shell
curl "https://api.happyapps.io/api/groups"
  -H "Authorization: BEARER access_token"
```

> The above command returns JSON structured like this:

```json
{
  "checkGroups": [
    {
      "id": 1,
      "account": {
        "id": 1
      },
      "availability": 99.87202932,
      "checks": [
        {
          "id": 3
        }
      ],
      "createIncident": true,
      "dateCreated": "2015-01-26T18:43:01Z",
      "deleted": false,
      "description": null,
      "health": 10,
      "history": null,
      "inUptime": true,
      "lastCheckStatus": null,
      "lastError": null,
      "lastErrorDate": null,
      "lastMessage": null,
      "lastMetric": null,
      "lastRunDate": "2015-05-16T14:14:15Z",
      "lastSuccessDate": null,
      "lastTimer": 246,
      "lastUpdated": "2015-05-16T14:14:15Z",
      "lastWarningDate": null,
      "minHappy": 1,
      "name": "My Group",
      "outageTime": 0,
      "severity": "critical"
    }
  ]  
}
```

This endpoint retrieves all groups and a list of checks associated with the group by id.

### HTTP Request

`GET https://api.happyapps.io/api/groups`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
max | 25 | The max number of results to return
offset | 0 | The offset of records you want to load
lastUpdated | null | A date filter, restricts query to only load groups updated more recent or equal to the date specified
deleted | undefined | if this param is specified you can load previously deleted checks. This is useful for synchronizing deleted records in your client side store.


<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Group


```shell
curl "https://api.happyapps.io/api/groups/1" \
  -H "Authorization: BEARER access_token"
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "checkGroup": {
    "id": 1,
    "account": {
      "id": 1
    },
    "availability": 99.87202932,
    "checks": [
      {
        "id": 3
      }
    ],
    "createIncident": true,
    "dateCreated": "2015-01-26T18:43:01Z",
    "deleted": false,
    "description": null,
    "health": 10,
    "history": null,
    "inUptime": true,
    "lastCheckStatus": null,
    "lastError": null,
    "lastErrorDate": null,
    "lastMessage": null,
    "lastMetric": null,
    "lastRunDate": "2015-05-16T14:14:15Z",
    "lastSuccessDate": null,
    "lastTimer": 246,
    "lastUpdated": "2015-05-16T14:14:15Z",
    "lastWarningDate": null,
    "minHappy": 1,
    "name": "My Group",
    "outageTime": 0,
    "severity": "critical"
  }
}
```

This endpoint retrieves a specific group.


### HTTP Request

`GET https://api.happyapps.io/api/groups/:id`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the group to retrieve

## Create a Group

```shell
curl -XPOST "https://api.happyapps.io/api/groups" \
  -H "Authorization: BEARER access_token" \
  -H "Content-Type: application/json" \
  -d '{"checkGoup":{
    "name": "My Group",
    "inUptime": true,
    "severity": "critical",
    "description": null,
    "happyAppCheckIds": [1,2,3]
  }}'
```

> The above command returns JSON structured like getting a single group: 

### HTTP Request

`POST https://api.happyapps.io/api/groups`

### JSON Check Parameters

Parameter | Default | Description
--------- | ------- | -----------
name      | null | A unique name scoped to your account for the group
description | null | Optional description field if you want to put more info there
inUptime  | true | Wether or not this group should affect account wide availability calculations.
severity  | critical | The severity level of incidents that are created when this group fails. They can be one of `info`, `warning`, or `critical`
happyAppCheckIds | null | Array of check ids to be placed within the group

## Updating a Group

```shell
curl -XPUT "https://api.happyapps.io/api/groups/1" \
  -H "Authorization: BEARER access_token" \
  -H "Content-Type: application/json" \
  -d '{"checkGroup":{
    "name": "My Group",
    "inUptime": true,
    "severity": "critical",
    "description": null,
    "happyAppCheckIds": [1,2,3]
  }}'
```

> The above command returns JSON structured like getting a single group: 

### HTTP Request

`PUT https://api.happyapps.io/api/groups/:id`

### JSON Check Parameters

Parameter | Default | Description
--------- | ------- | -----------
name      | null | A unique name scoped to your account for the group
description | null | Optional description field if you want to put more info there
inUptime  | true | Wether or not this group should affect account wide availability calculations.
severity  | critical | The severity level of incidents that are created when this group fails. They can be one of `info`, `warning`, or `critical`
happyAppCheckIds | null | Array of check ids to be placed within the group

## Mute a Group


```shell
curl -XPUT "https://api.happyapps.io/api/groups/1/mute" \
  -H "Authorization: BEARER access_token" \
  -H "Content-Type: application/json" \
  -d '{"enabled":true}'
```

> The above command returns JSON structured like this:

```json
{
  "muteState": "QUARANTINED",
  "success": true
}
```

This endpoint can be used to toggle the mute state of a Group.

### HTTP Request

`PUT https://api.happyapps.io/api/groups/:id/mute`

### JSON Parameters

Parameter | Description
--------- | -----------
enabled | Set this to true or false depending on if you want to mute or unmute a group.


## Delete a Group

```shell
curl -XDELETE "https://api.happyapps.io/api/groups/1" \
  -H "Authorization: BEARER access_token"
```

> The above command returns JSON Structured like this:

```json
{
  "success": true
}
```

A Deleted group can be fetched optionally from the GET api for sync verification but can no longer be used or updated.

