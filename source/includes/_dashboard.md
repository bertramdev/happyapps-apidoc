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
      "class": "com.happyapps.HappyApp",
      "id": 1,
      "account": {
        "class": "com.bertramlabs.plugins.Account",
        "id": 1
      },
      "active": true,
      "allCheckStatus": null,
      "availability": 99.99282407,
      "checkGroups": [
        
      ],
      "checks": [
        {
          "class": "com.happyapps.HappyCheck",
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
      "class": "com.happyapps.HappyCheckType",
      "id": 1,
      "code": "webGetCheck",
      "createIncident": true,
      "defaultInterval": 60000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "inputTemplate": "\/templates\/input\/webCheck",
      "metricName": "response",
      "name": "Web Check",
      "pushOnly": false,
      "queueName": "happyappsWebGetCheck",
      "script": null,
      "statusTemplate": "\/templates\/status\/webCheck",
      "tunnelSupported": true,
      "viewTemplate": "\/templates\/view\/webCheck"
    },
    {
      "class": "com.happyapps.HappyCheckType",
      "id": 2,
      "code": "mysqlCheck",
      "createIncident": true,
      "defaultInterval": 60000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "inputTemplate": "\/templates\/input\/mysqlCheck",
      "metricName": "result",
      "name": "MySQL Check",
      "pushOnly": false,
      "queueName": "happyappsMySqlCheck",
      "script": null,
      "statusTemplate": "\/templates\/status\/mysqlCheck",
      "tunnelSupported": true,
      "viewTemplate": "\/templates\/view\/mysqlCheck"
    },
    {
      "class": "com.happyapps.HappyCheckType",
      "id": 3,
      "code": "mongoCheck",
      "createIncident": true,
      "defaultInterval": 300000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "inputTemplate": "\/templates\/input\/mongoCheck",
      "metricName": "result",
      "name": "Mongo Check",
      "pushOnly": false,
      "queueName": "happyappsMongoCheck",
      "script": null,
      "statusTemplate": "\/templates\/status\/mongoCheck",
      "tunnelSupported": true,
      "viewTemplate": "\/templates\/view\/mongoCheck"
    },
    {
      "class": "com.happyapps.HappyCheckType",
      "id": 4,
      "code": "elasticSearchCheck",
      "createIncident": true,
      "defaultInterval": 60000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "inputTemplate": "\/templates\/input\/elasticCheck",
      "metricName": "cluster status",
      "name": "Elastic Search Check",
      "pushOnly": false,
      "queueName": "happyappsElasticSearchCheck",
      "script": null,
      "statusTemplate": "\/templates\/status\/elasticCheck",
      "tunnelSupported": true,
      "viewTemplate": "\/templates\/view\/elasticCheck"
    },
    {
      "class": "com.happyapps.HappyCheckType",
      "id": 5,
      "code": "riakCheck",
      "createIncident": true,
      "defaultInterval": 300000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "inputTemplate": "\/templates\/input\/riakCheck",
      "metricName": "write time",
      "name": "Riak Check",
      "pushOnly": false,
      "queueName": "happyappsRiakCheck",
      "script": null,
      "statusTemplate": "\/templates\/status\/riakCheck",
      "tunnelSupported": true,
      "viewTemplate": "\/templates\/view\/riakCheck"
    },
    {
      "class": "com.happyapps.HappyCheckType",
      "id": 6,
      "code": "redisCheck",
      "createIncident": true,
      "defaultInterval": 300000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "inputTemplate": "\/templates\/input\/redisCheck",
      "metricName": "key count",
      "name": "Redis Check",
      "pushOnly": false,
      "queueName": "happyappsRedisCheck",
      "script": null,
      "statusTemplate": "\/templates\/status\/redisCheck",
      "tunnelSupported": true,
      "viewTemplate": "\/templates\/view\/redisCheck"
    },
    {
      "class": "com.happyapps.HappyCheckType",
      "id": 7,
      "code": "rabbitCheck",
      "createIncident": true,
      "defaultInterval": 60000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "inputTemplate": "\/templates\/input\/rabbitCheck",
      "metricName": "queue count",
      "name": "Rabbit MQ Check",
      "pushOnly": false,
      "queueName": "happyappsRabbitMqCheck",
      "script": null,
      "statusTemplate": "\/templates\/status\/rabbitCheck",
      "tunnelSupported": true,
      "viewTemplate": "\/templates\/view\/rabbitCheck"
    },
    {
      "class": "com.happyapps.HappyCheckType",
      "id": 9,
      "code": "postgresCheck",
      "createIncident": true,
      "defaultInterval": 300000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "inputTemplate": "\/templates\/input\/postgresCheck",
      "metricName": "result",
      "name": "Postgres Check",
      "pushOnly": false,
      "queueName": "happyappsPostgresCheck",
      "script": null,
      "statusTemplate": "\/templates\/status\/postgresCheck",
      "tunnelSupported": true,
      "viewTemplate": "\/templates\/view\/postgresCheck"
    },
    {
      "class": "com.happyapps.HappyCheckType",
      "id": 10,
      "code": "sqlCheck",
      "createIncident": true,
      "defaultInterval": 300000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "inputTemplate": "\/templates\/input\/sqlCheck",
      "metricName": "result",
      "name": "Microsoft SQL Server",
      "pushOnly": false,
      "queueName": "happyappsSqlServerCheck",
      "script": null,
      "statusTemplate": "\/templates\/status\/sqlCheck",
      "tunnelSupported": true,
      "viewTemplate": "\/templates\/view\/sqlCheck"
    },
    {
      "class": "com.happyapps.HappyCheckType",
      "id": 11,
      "code": "socketCheck",
      "createIncident": true,
      "defaultInterval": 60000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "inputTemplate": "\/templates\/input\/socketCheck",
      "metricName": "response",
      "name": "Socket Check",
      "pushOnly": false,
      "queueName": "happyappsSocketCheck",
      "script": null,
      "statusTemplate": "\/templates\/status\/socketCheck",
      "tunnelSupported": true,
      "viewTemplate": "\/templates\/view\/socketCheck"
    },
    {
      "class": "com.happyapps.HappyCheckType",
      "id": 12,
      "code": "pushCheck",
      "createIncident": true,
      "defaultInterval": 300000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "inUptime": true,
      "inputTemplate": "\/templates\/input\/pushCheck",
      "metricName": "result",
      "name": "Push API Check",
      "pushOnly": true,
      "queueName": null,
      "script": null,
      "statusTemplate": "\/templates\/status\/pushCheck",
      "tunnelSupported": false,
      "viewTemplate": "\/templates\/view\/pushCheck"
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
