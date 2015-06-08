# Dashboard Stats

Ever wonder how to extract all those useful statistics from the dashboard? Happy Apps provides an API endpoint for fetching all your dashboard stats. This could come in handy if one wanted to integrate a Happy Apps dashboard into their own monitoring website or service.

## Getting Dashboard Stats

```shell
curl "https://api.happyapps.io/api/dashboard"
  -H "Authorization: BEARER access_token"
```

> Returns JSON of the following format

```json
{
  "appList": [
    {
      "id": 1,
      "account": {
        "id": 1
      },
      "active": true,
      "allCheckStatus": null,
      "availability": 99.99282407,
      "checkGroups": [
        
      ],
      "checks": [
        {
          "id": 1
        }
      ],
      "createIncident": true,
      "dateCreated": "2015-01-27T01:28:56Z",
      "deleted": false,
      "description": null,
      "health": 10,
      "history": null,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "lastCheckStatus": null,
      "lastError": null,
      "lastErrorDate": null,
      "lastMessage": null,
      "lastRunDate": "2015-06-04T15:10:00Z",
      "lastSuccessDate": null,
      "lastTimer": 605,
      "lastUpdated": "2015-06-04T15:10:01Z",
      "lastWarningDate": null,
      "name": "My App",
      "severity": "critical",
      "urlName": null
    }
  ],
  "openIncidents": [
    
  ],
  "checkTypes": [
    {
      "id": 1,
      "code": "webGetCheck",
      "createIncident": true,
      "defaultInterval": 60000,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "metricName": "response",
      "name": "Web Check",
      "tunnelSupported": true
    },
    {
      "id": 2,
      "code": "mysqlCheck",
      "createIncident": true,
      "defaultInterval": 60000,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "metricName": "result",
      "name": "MySQL Check",
      "tunnelSupported": true
    },
    {
      "id": 3,
      "code": "mongoCheck",
      "createIncident": true,
      "defaultInterval": 300000,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "metricName": "result",
      "name": "Mongo Check",
      "tunnelSupported": true
    },
    {
      "id": 4,
      "code": "elasticSearchCheck",
      "createIncident": true,
      "defaultInterval": 60000,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "metricName": "cluster status",
      "name": "Elastic Search Check",
      "tunnelSupported": true
    },
    {
      "id": 5,
      "code": "riakCheck",
      "createIncident": true,
      "defaultInterval": 300000,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "metricName": "write time",
      "name": "Riak Check",
      "tunnelSupported": true
    },
    {
      "id": 6,
      "code": "redisCheck",
      "createIncident": true,
      "defaultInterval": 300000,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "metricName": "key count",
      "name": "Redis Check",
      "tunnelSupported": true
    },
    {
      "id": 7,
      "code": "rabbitCheck",
      "createIncident": true,
      "defaultInterval": 60000,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "metricName": "queue count",
      "name": "Rabbit MQ Check",
      "tunnelSupported": true
    },
    {
      "id": 9,
      "code": "postgresCheck",
      "createIncident": true,
      "defaultInterval": 300000,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "metricName": "result",
      "name": "Postgres Check",
      "tunnelSupported": true
    },
    {
      "id": 10,
      "code": "sqlCheck",
      "createIncident": true,
      "defaultInterval": 300000,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "metricName": "result",
      "name": "Microsoft SQL Server",
      "tunnelSupported": true
    },
    {
      "id": 11,
      "code": "socketCheck",
      "createIncident": true,
      "defaultInterval": 60000,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "metricName": "response",
      "name": "Socket Check",
      "tunnelSupported": true
    },
    {
      "id": 12,
      "code": "pushCheck",
      "createIncident": true,
      "defaultInterval": 300000,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "metricName": "result",
      "name": "Push API Check",
      "tunnelSupported": false
    },
    {
      "id": 13,
      "code": "pingCheck",
      "createIncident": true,
      "defaultInterval": 300000,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "metricName": "result",
      "name": "Ping Check",
      "tunnelSupported": true
    }
  ],
  "history": [
    {
      "checkId": 215,
      "accountId": 1,
      "status": null,
      "lastTimer": 171,
      "lastErrorDate": "2015-05-18T09:24:00.000Z",
      "lastStats": null,
      "lastRunDate": "2015-06-04T15:10:00Z",
      "health": 10,
      "lastWarningDate": null,
      "inUptime": true,
      "createIncident": true,
      "lastCheckStatus": "success",
      "_id": "1433430600403215Aee7Ly9Qep",
      "lastBoxStats": null,
      "lastSuccessDate": "2015-06-04T15:10:00.169Z",
      "lastMetric": "200",
      "name": "MadTrack",
      "outageTime": 0,
      "lastMessage": "http 200",
      "checkTypeId": 1,
      "lastError": "http error: Read timed out",
      "internalError": false
    }
  ],
  "appStatus": {
    "avgHealth": 10,
    "avgResponseTime": 274,
    "warningApps": 0,
    "warningChecks": 0,
    "failApps": 0,
    "failChecks": 0,
    "successApps": 2,
    "mutedApps": 0,
    "successChecks": 8,
    "mutedChecks": 0,
    "allSuccess": true
  },
  "availability": 99.777486775714
}
```

This endpoint retrieves an overall `appStatus` with counts for the different states of your checks,groups, and apps. It also provides an account wide `availability`. Other features include recently run check history, a check list, and an app list for viewing.

### HTTP Request

`GET https://api.happyapps.io/api/dashboard`
