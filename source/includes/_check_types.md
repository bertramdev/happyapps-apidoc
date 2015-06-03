# Check Types

A set of APIs for fetching a list of available check types is also provided. This API can make it useful for associating a check type code to an ID for check `GET` and `POST` requests.

## Get All Check Types

```shell
curl "https://api.happyapps.io/api/check-types"
  -H "Authorization: BEARER access_token"
```

> The above command returns JSON structured like this

```json
{
  "checkTypes": [
    {
      "class": "com.happyapps.HappyCheckType",
      "code": "webGetCheck",
      "createIncident": true,
      "defaultInterval": 60000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "id": 1,
      "inUptime": true,
      "inputTemplate": "/templates/input/webCheck",
      "metricName": "response",
      "name": "Web Check",
      "queueName": "happyappsWebGetCheck",
      "script": null,
      "statusTemplate": "/templates/status/webCheck",
      "tunnelSupported": false,
      "viewTemplate": "/templates/view/webCheck"
    },
    {
      "class": "com.happyapps.HappyCheckType",
      "code": "mysqlCheck",
      "createIncident": true,
      "defaultInterval": 60000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "id": 2,
      "inUptime": true,
      "inputTemplate": "/templates/input/mysqlCheck",
      "metricName": "result",
      "name": "MySQL Check",
      "queueName": "happyappsMySqlCheck",
      "script": null,
      "statusTemplate": "/templates/status/mysqlCheck",
      "tunnelSupported": false,
      "viewTemplate": "/templates/view/mysqlCheck"
    },
    {
      "class": "com.happyapps.HappyCheckType",
      "code": "mongoCheck",
      "createIncident": true,
      "defaultInterval": 300000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "id": 3,
      "inUptime": true,
      "inputTemplate": "/templates/input/mongoCheck",
      "metricName": "result",
      "name": "Mongo Check",
      "queueName": "happyappsMongoCheck",
      "script": null,
      "statusTemplate": "/templates/status/mongoCheck",
      "tunnelSupported": false,
      "viewTemplate": "/templates/view/mongoCheck"
    },
    {
      "class": "com.happyapps.HappyCheckType",
      "code": "elasticSearchCheck",
      "createIncident": true,
      "defaultInterval": 60000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "id": 4,
      "inUptime": true,
      "inputTemplate": "/templates/input/elasticCheck",
      "metricName": "cluster status",
      "name": "Elastic Search Check",
      "queueName": "happyappsElasticSearchCheck",
      "script": null,
      "statusTemplate": "/templates/status/elasticCheck",
      "tunnelSupported": false,
      "viewTemplate": "/templates/view/elasticCheck"
    },
    {
      "class": "com.happyapps.HappyCheckType",
      "code": "riakCheck",
      "createIncident": true,
      "defaultInterval": 300000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "id": 5,
      "inUptime": true,
      "inputTemplate": "/templates/input/riakCheck",
      "metricName": "write time",
      "name": "Riak Check",
      "queueName": "happyappsRiakCheck",
      "script": null,
      "statusTemplate": "/templates/status/riakCheck",
      "tunnelSupported": false,
      "viewTemplate": "/templates/view/riakCheck"
    },
    {
      "class": "com.happyapps.HappyCheckType",
      "code": "redisCheck",
      "createIncident": true,
      "defaultInterval": 300000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "id": 6,
      "inUptime": true,
      "inputTemplate": "/templates/input/redisCheck",
      "metricName": "key count",
      "name": "Redis Check",
      "queueName": "happyappsRedisCheck",
      "script": null,
      "statusTemplate": "/templates/status/redisCheck",
      "tunnelSupported": false,
      "viewTemplate": "/templates/view/redisCheck"
    },
    {
      "class": "com.happyapps.HappyCheckType",
      "code": "rabbitCheck",
      "createIncident": true,
      "defaultInterval": 60000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "id": 7,
      "inUptime": true,
      "inputTemplate": "/templates/input/rabbitCheck",
      "metricName": "queue count",
      "name": "Rabbit MQ Check",
      "queueName": "happyappsRabbitMqCheck",
      "script": null,
      "statusTemplate": "/templates/status/rabbitCheck",
      "tunnelSupported": false,
      "viewTemplate": "/templates/view/rabbitCheck"
    },
    {
      "class": "com.happyapps.HappyCheckType",
      "code": "postgresCheck",
      "createIncident": true,
      "defaultInterval": 300000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "id": 8,
      "inUptime": true,
      "inputTemplate": "/templates/input/postgresCheck",
      "metricName": "result",
      "name": "Postgres Check",
      "queueName": "happyappsPostgresCheck",
      "script": null,
      "statusTemplate": "/templates/status/postgresCheck",
      "tunnelSupported": false,
      "viewTemplate": "/templates/view/postgresCheck"
    },
    {
      "class": "com.happyapps.HappyCheckType",
      "code": "sqlCheck",
      "createIncident": true,
      "defaultInterval": 300000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "id": 9,
      "inUptime": true,
      "inputTemplate": "/templates/input/sqlCheck",
      "metricName": "result",
      "name": "Microsoft SQL Server",
      "queueName": "happyappsSqlServerCheck",
      "script": null,
      "statusTemplate": "/templates/status/sqlCheck",
      "tunnelSupported": false,
      "viewTemplate": "/templates/view/sqlCheck"
    },
    {
      "class": "com.happyapps.HappyCheckType",
      "code": "socketCheck",
      "createIncident": true,
      "defaultInterval": 60000,
      "execMethod": null,
      "execService": null,
      "iconPath": null,
      "iconType": "upload",
      "id": 10,
      "inUptime": true,
      "inputTemplate": "/templates/input/socketCheck",
      "metricName": "response",
      "name": "Socket Check",
      "queueName": "happyappsSocketCheck",
      "script": null,
      "statusTemplate": "/templates/status/socketCheck",
      "tunnelSupported": false,
      "viewTemplate": "/templates/view/socketCheck"
    }
  ]
}
```

### HTTP Request

`GET https://api.happyapps.io/api/check-types`

## Get Specific Check Type

```shell
curl "https://api.happyapps.io/api/check-types/10"
  -H "Authorization: BEARER access_token"
```

> The above command returns JSON structured like this

```json
{
"success": true,
"checkType": {
    "class": "com.happyapps.HappyCheckType",
    "code": "socketCheck",
    "createIncident": true,
    "defaultInterval": 60000,
    "execMethod": null,
    "execService": null,
    "iconPath": null,
    "iconType": "upload",
    "id": 10,
    "inUptime": true,
    "inputTemplate": "/templates/input/socketCheck",
    "metricName": "response",
    "name": "Socket Check",
    "queueName": "happyappsSocketCheck",
    "script": null,
    "statusTemplate": "/templates/status/socketCheck",
    "tunnelSupported": false,
    "viewTemplate": "/templates/view/socketCheck"    
  }
}
```
### HTTP Request

`GET https://api.happyapps.io/api/check-types/1`

