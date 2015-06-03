# Incidents

Incidents are used to keep track of failed checks, groups, and apps. They can be used to keep a running history of what failed and when. They can also be updated to provide notes and resolution information. An incident can also be scoped to an app, many checks, or many groups depending on your defined heirarchy.

## Get All Incidents

```shell
curl "https://api.happyapps.io/api/incidents"
  -H "Authorization: BEARER access_token"
```

> The above command returns JSON structured like this:

```json
{
  "openIncidents": [
    
  ],
  "incidentStats": {
    "today": 0,
    "week": 0,
    "month": 32
  },
  "incidents": [
    {
      "class": "com.happyapps.HappyIncident",
      "id": 122,
      "account": {
        "class": "com.bertramlabs.plugins.Account",
        "id": 1
      },
      "app": null,
      "autoClose": true,
      "autoManaged": true,
      "channelId": "f8d47f3e-1bbb-4b7e-9e53-8c396acc6e86",
      "checkGroups": [
        
      ],
      "checks": [
        {
          "class": "com.happyapps.HappyCheck",
          "id": 1
        }
      ],
      "comment": null,
      "dateCreated": "2015-05-31T19:57:29Z",
      "duration": 65286,
      "endDate": "2015-05-14T21:12:45Z",
      "inUptime": true,
      "incidentEvents": [
        {
          "class": "com.happyapps.HappyIncidentEvent",
          "id": 268
        },
        {
          "class": "com.happyapps.HappyIncidentEvent",
          "id": 267
        }
      ],
      "lastCheckTime": "2015-05-14T21:11:40Z",
      "lastError": "http error: www.googleFAILNOW.com: nodename nor servname provided, or not known",
      "lastMessage": null,
      "lastUpdated": "2015-05-31T19:57:41Z",
      "name": null,
      "notificationEvents": [
        {
          "class": "com.happyapps.HappyIncidentNotifyEvent",
          "id": 196
        },
        {
          "class": "com.happyapps.HappyIncidentNotifyEvent",
          "id": 195
        }
      ],
      "resolution": null,
      "severity": "critical",
      "severityId": 20,
      "startDate": "2015-05-14T21:11:40Z",
      "status": "closed",
      "visibility": "private"
    }
  ],
  "incidentCount": 109
```

This endpoint retrieves all open incidents, a pageable list of all incidents, and a stat summary of incidents

### HTTP Request

`GET https://api.happyapps.io/api/incidents`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
max | 25 | The max number of results to return
offset | 0 | The offset of records you want to load
lastUpdated | null | A date filter, restricts query to only load incidents updated more recent or equal to the date specified

