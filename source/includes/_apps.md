# Apps

Apps are a useful means to organize a set of checks and groups. You can assign any set of checks or groups to an app to define what items in your infrastructure affect an overall applications health. This is useful for scoping incidents to the engineering team responsible for an application and also to provide an overview of what a check failure might actually be affecting throughout your environment.

## Get All Apps

```shell
curl "https://api.happyapps.io/api/apps"
  -H "Authorization: BEARER access_token"
```

> The above command returns JSON structured like this:

```json
{
  "apps": [
    {
      "class": "com.happyapps.HappyApp",
      "id": 2,
      "account": {
        "class": "com.bertramlabs.plugins.Account",
        "id": 1
      },
      "active": true,
      "allCheckStatus": null,
      "availability": null,
      "checkGroups": [
        
      ],
      "checks": [
        
      ],
      "createIncident": true,
      "dateCreated": "2015-02-09T21:14:51Z",
      "deleted": false,
      "description": null,
      "health": 9,
      "history": null,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "lastCheckStatus": null,
      "lastError": null,
      "lastErrorDate": null,
      "lastMessage": null,
      "lastRunDate": null,
      "lastSuccessDate": null,
      "lastTimer": 0,
      "lastUpdated": "2015-02-09T21:14:51Z",
      "lastWarningDate": null,
      "name": "My blank app",
      "severity": "critical",
      "urlName": null
    }
  ],
  "appCount": 1
}
```

This endpoint retrieves all apps and a list of checks and groups associated with the app by id.

### HTTP Request

`GET https://api.happyapps.io/api/apps`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
max | 25 | The max number of results to return
offset | 0 | The offset of records you want to load
lastUpdated | null | A date filter, restricts query to only load apps updated more recent or equal to the date specified
deleted | undefined | if this param is specified you can load previously deleted apps. This is useful for synchronizing deleted records in your client side store.


<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific App


```shell
curl "https://api.happyapps.io/api/apps/1" \
  -H "Authorization: BEARER access_token"
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "app": {
    "class": "com.happyapps.HappyApp",
    "id": 2,
    "account": {
      "class": "com.bertramlabs.plugins.Account",
      "id": 1
    },
    "active": true,
    "allCheckStatus": null,
    "availability": null,
    "checkGroups": [
      
    ],
    "checks": [
      
    ],
    "createIncident": true,
    "dateCreated": "2015-02-09T21:14:51Z",
    "deleted": false,
    "description": null,
    "health": 9,
    "history": null,
    "iconPath": null,
    "iconType": "upload",
    "inUptime": true,
    "lastCheckStatus": null,
    "lastError": null,
    "lastErrorDate": null,
    "lastMessage": null,
    "lastRunDate": null,
    "lastSuccessDate": null,
    "lastTimer": 0,
    "lastUpdated": "2015-02-09T21:14:51Z",
    "lastWarningDate": null,
    "name": "My blank app",
    "severity": "critical",
    "urlName": null
  }
}
```

This endpoint retrieves a specific app.


### HTTP Request

`GET https://api.happyapps.io/api/apps/:id`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the app to retrieve

## Create a App

```shell
curl -XPOST "https://api.happyapps.io/api/apps" \
  -H "Authorization: BEARER access_token" \
  -H "Content-Type: application/json" \
  -d '{"app":{
    "name": "My App",
    "inUptime": true,
    "severity": "critical",
    "description": null,
    "happyAppCheckIds": [1,2,3],
    "happyAppCheckGroupIds": [1,2,3]
  }}'
```

> The above command returns JSON structured like getting a single app: 

### HTTP Request

`POST https://api.happyapps.io/api/apps`

### JSON Check Parameters

Parameter | Default | Description
--------- | ------- | -----------
name      | null | A unique name scoped to your account for the app
description | null | Optional description field if you want to put more info there
inUptime  | true | Wether or not this app should affect account wide availability calculations.
severity  | critical | The severity level of incidents that are created when this app fails. They can be one of `info`, `warning`, or `critical`
happyAppCheckIds | null | Array of check ids to be placed within the app
happyAppCheckGroupIds | null | Array of group ids to be placed within the app

## Updating a App

```shell
curl -XPUT "https://api.happyapps.io/api/apps/1" \
  -H "Authorization: BEARER access_token" \
  -H "Content-Type: application/json" \
  -d '{"app":{
    "name": "My App",
    "inUptime": true,
    "severity": "critical",
    "description": null,
    "happyAppCheckIds": [1,2,3],
    "happyAppCheckGroupIds": [1,2,3]
  }}'
```

> The above command returns JSON structured like getting a single app: 

### HTTP Request

`PUT https://api.happyapps.io/api/apps/:id`

### JSON Check Parameters

Parameter | Default | Description
--------- | ------- | -----------
name      | null | A unique name scoped to your account for the app
description | null | Optional description field if you want to put more info there
inUptime  | true | Wether or not this app should affect account wide availability calculations.
severity  | critical | The severity level of incidents that are created when this app fails. They can be one of `info`, `warning`, or `critical`
happyAppCheckIds | null | Array of check ids to be placed within the app
happyAppCheckGroupIds | null | Array of group ids to be placed within the app

## Mute a App


```shell
curl -XPUT "https://api.happyapps.io/api/apps/1/mute" \
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

This endpoint can be used to toggle the mute state of a App.

### HTTP Request

`PUT https://api.happyapps.io/api/apps/:id/mute`

### JSON Parameters

Parameter | Description
--------- | -----------
enabled | Set this to true or false depending on if you want to mute or unmute a app.


## Delete a App

```shell
curl -XDELETE "https://api.happyapps.io/api/apps/1" \
  -H "Authorization: BEARER access_token"
```

> The above command returns JSON Structured like this:

```json
{
  "success": true
}
```

A Deleted app can be fetched optionally from the GET api for sync verification but can no longer be used or updated.

