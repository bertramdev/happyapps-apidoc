# Checks

## Get All Checks

```shell
curl "https://api.happyapps.io/api/checks"
  -H "Authorization: BEARER access_token"
```

> The above command returns JSON structured like this:

```json
{
  "checks": [
    {
      "class": "com.happyapps.HappyCheck",
      "id": 798,
      "account": {
        "class": "com.bertramlabs.plugins.Account",
        "id": 1
      },
      "active": true,
      "availability": 99.9804109,
      "checkAgent": null,
      "checkIntegrations": [
        
      ],
      "checkInterval": 300,
      "checkSpec": null,
      "checkType": {
        "class": "com.happyapps.HappyCheckType",
        "id": 1
      },
      "config": "{\n  \"webMethod\" : \"GET\",\n  \"webUrl\" : \"http:\\\/\\\/google.com\"\n}",
      "createIncident": true,
      "dateCreated": "2015-05-16T12:05:23Z",
      "deleted": false,
      "description": null,
      "endDate": null,
      "health": 10,
      "history": "{\"checkDates\":[1433339580607,1433339595119,1433339613169,1433339625412,1433339641010,1433339655209,1433339670178,1433339687802,1433339700471,1433339715171,1433339730710,1433339745351,1433339764299,1433339775508,1433339790377,1433339805373,1433339820944,1433339835996,1433339850317,1433339865833,1433339880884,1433339895489,1433339910554,1433339925660,1433339940875,1433339956143,1433339970551,1433339985179,1433340000961,1433340015765],\"successList\":[true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true],\"healthList\":[10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10],\"timerList\":[347,410,338,337,365,361,373,374,358,337,350,505,342,338,358,359,381,354,353,377,342,344,349,363,329,352,350,348,356,345]}",
      "inUptime": true,
      "lastBoxStats": null,
      "lastCheckStatus": "success",
      "lastError": "http error: Read timed out",
      "lastErrorDate": "2015-05-18T09:25:15Z",
      "lastMessage": "http 200",
      "lastMetric": "200",
      "lastRunDate": "2015-06-03T14:00:16Z",
      "lastStats": null,
      "lastSuccessDate": "2015-06-03T14:00:16Z",
      "lastTimer": 345,
      "lastUpdated": "2015-06-03T14:00:16Z",
      "lastWarningDate": null,
      "name": "Purity Plus",
      "nextRunDate": "2015-06-03T14:00:16Z",
      "outageTime": 0,
      "severity": "critical",
      "startDate": null
    }
  ]
}
```

This endpoint retrieves all checks and their json encoded config attributes based on check type. These are encryped in the databse.

### HTTP Request

`GET https://api.happyapps.io/api/checks`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
max | 25 | The max number of results to return
offset | 0 | The offset of records you want to load
lastUpdated | null | A date filter, restricts query to only load checks updated more recent or equal to the date specified
deleted | undefined | if this param is specified you can load previously deleted checks. This is useful for synchronizing deleted records in your client side store.


<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Check


```shell
curl "https://api.happyapps.io/api/checks/1" \
  -H "Authorization: BEARER access_token"
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "check:" {
    "class": "com.happyapps.HappyCheck",
    "id": 798,
    "account": {
      "class": "com.bertramlabs.plugins.Account",
      "id": 1
    },
    "active": true,
    "availability": 99.9804109,
    "checkAgent": null,
    "checkIntegrations": [
      
    ],
    "checkInterval": 300,
    "checkSpec": null,
    "checkType": {
      "class": "com.happyapps.HappyCheckType",
      "id": 1
    },
    "config": "{\n  \"webMethod\" : \"GET\",\n  \"webUrl\" : \"http:\\\/\\\/google.com\"\n}",
    "createIncident": true,
    "dateCreated": "2015-05-16T12:05:23Z",
    "deleted": false,
    "description": null,
    "endDate": null,
    "health": 10,
    "history": "{\"checkDates\":[1433339580607,1433339595119,1433339613169,1433339625412,1433339641010,1433339655209,1433339670178,1433339687802,1433339700471,1433339715171,1433339730710,1433339745351,1433339764299,1433339775508,1433339790377,1433339805373,1433339820944,1433339835996,1433339850317,1433339865833,1433339880884,1433339895489,1433339910554,1433339925660,1433339940875,1433339956143,1433339970551,1433339985179,1433340000961,1433340015765],\"successList\":[true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true,true],\"healthList\":[10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10],\"timerList\":[347,410,338,337,365,361,373,374,358,337,350,505,342,338,358,359,381,354,353,377,342,344,349,363,329,352,350,348,356,345]}",
    "inUptime": true,
    "lastBoxStats": null,
    "lastCheckStatus": "success",
    "lastError": "http error: Read timed out",
    "lastErrorDate": "2015-05-18T09:25:15Z",
    "lastMessage": "http 200",
    "lastMetric": "200",
    "lastRunDate": "2015-06-03T14:00:16Z",
    "lastStats": null,
    "lastSuccessDate": "2015-06-03T14:00:16Z",
    "lastTimer": 345,
    "lastUpdated": "2015-06-03T14:00:16Z",
    "lastWarningDate": null,
    "name": "Purity Plus",
    "nextRunDate": "2015-06-03T14:00:16Z",
    "outageTime": 0,
    "severity": "critical",
    "startDate": null
  }
}
```

This endpoint retrieves a specific check.


### HTTP Request

`GET https://api.happyapps.io/api/checks/:id`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the check to retrieve

## Create a Check

```shell
curl -XPOST "https://api.happyapps.io/api/checks" \
  -H "Authorization: BEARER access_token" \
  -H "Content-Type: application/json" \
  -d '{"check":{
    "name": "My Check",
    "checkType": {"code": "webGetCheck"},
    "inUptime": true,
    "severity": "critical",
    "description": null,
    "checkInterval": 300,
    "checkAgent": null,
    "active": true,
    "config": "{\n  \"webMethod\" : \"GET\",\n  \"webUrl\" : \"http:\\\/\\\/google.com\"\n}",
  }}'
```

> The above command returns JSON structured like getting a single check: 

### HTTP Request

`POST https://api.happyapps.io/api/checks`

### JSON Check Parameters

Parameter | Default | Description
--------- | ------- | -----------
name      | null | A unique name scoped to your account for the check
description | null | Optional description field if you want to put more info there
checkType | null | The check type you want to create should be passed by code `{"code": "webGetCheck"}`
checkInterval | 300 | The number of seconds you want between check runs (can go as low as one minute if payment plan permits)
inUptime  | true | Wether or not this check should affect account wide availability calculations.
active    | true | Wether or not the check should be marked active for run
severity  | critical | The severity level of incidents that are created when this check fails. They can be one of `info`, `warning`, or `critical`
checkAgent | null | Can specify the checkAgent you want to run the check with i.e. `{"id": 1}`
config | null | A JSON Encoded list of parameters that varies by check type. See below for more info

## Updating a Check

```shell
curl -XPUT "https://api.happyapps.io/api/checks/1" \
  -H "Authorization: BEARER access_token" \
  -H "Content-Type: application/json" \
  -d '{"check":{
    "name": "My Check",
    "checkType": {"code": "webGetCheck"},
    "inUptime": true,
    "severity": "critical",
    "description": null,
    "checkInterval": 300,
    "checkAgent": null,
    "active": true,
    "config": "{\n  \"webMethod\" : \"GET\",\n  \"webUrl\" : \"http:\\\/\\\/google.com\"\n}",
  }}'
```

> The above command returns JSON structured like getting a single check: 

### HTTP Request

`PUT https://api.happyapps.io/api/checks/:id`

### JSON Check Parameters

Parameter | Default | Description
--------- | ------- | -----------
name      | null | A unique name scoped to your account for the check
description | null | Optional description field if you want to put more info there
checkType | null | The check type you want to create should be passed by code `{"code": "webGetCheck"}`
checkInterval | 300 | The number of seconds you want between check runs (can go as low as one minute if payment plan permits)
inUptime  | true | Wether or not this check should affect account wide availability calculations.
active    | true | Wether or not the check should be marked active for run
severity  | critical | The severity level of incidents that are created when this check fails. They can be one of `info`, `warning`, or `critical`
checkAgent | null | Can specify the checkAgent you want to run the check with i.e. `{"id": 1}`
config | null | A JSON Encoded list of parameters that varies by check type. See below for more info

## Check Types and Options

We support a wide variety of check types. Each check type varies in its config payload for determining how the check should be run.


> Creates a Web type Check

### Web Get Check

```json
{
  "check": {
    "name": "My Web Check",
    "checkType": {"code": "webGetCheck"},
    "config": "{\"webMethod\":\"GET\",\"webUrl\": \"http:\\\/\\\/google.com\", \"checkUser\":\"basicUser\",\"checkPassword\":\"basicPassword\", \"webTextMatch\": \"Login\", \"textCheckOn\": \"on\"}"
  }
}
```

Code: `webGetCheck`

The Web check allows you to perform a standard web request style check and validate the response came back successfully or even check for matching text within the result. There are several `config` parameters available for use with this type of check

Parameter | Requirement | Description
--------- | ----------- | -----------
webMethod | Yes         | The HTTP Method to use for testing (GET or POST)
webUrl    | Yes         | The Web URL you wish to use to run a check on
checkUser | No          | If you want to use HTTP Basic auth fill this in
checkPassword | No      | If you want to use HTTP Basic auth fill in this password.
textCheckOn   | No      | Set value to "on" if you want to turn on text matching
webTextMatch  | No      | Set the string you want to check for

### Mysql Check

```json
{
  "check": {
    "name": "MySql Check",
    "checkType": {"code": "mysqlCheck"},
    "config": "{\"dbHost\":\"db.example.org\",\"dbPort\": \"3306\", \"dbUser\":\"basicUser\",\"dbPassword\":\"basicPassword\", \"dbName\": \"mydb\", \"dbQuery\": \"select 1\", \"checkOperator\": \"lt\", \"checkResult\": 2}"
  }
}
```

Code: `mysqlCheck`

The MySQL Check allows you not only to confirm that a mysql database is up and running but also allows you to run a query and test the result value. This can be useful for doing a slow query check or just making sure something isnt growing out of control.

Parameter | Requirement | Description
--------- | ----------- | -----------
dbHost    | Yes         | The hostname / ipaddress of the mysql database
dbPort    | Yes         | The MySQL Port (defaults to 3306)
dbUser    | Yes         | The Database username
dbPassword | Yes        | The Database password (remember this gets encrypted)
dbName    | Yes         | The database name you would like to connect to
checkOperator  | No     | Can be set to lt (less than), gt (greater than), equal (Equal to) for comparison
checkResult | No        | Numerical value to compare the check result against. 

<aside class="notice">More often than not you will not want to directly connect to your mysql database on the open web. There are some options here. One is to use ssh tunneling which can be configured via adding some additional parameters to the config json (See the section on SSH Checks). Another option is to run our agent with an upgraded plan where the check can run from within a firewall.</aside>

### SQL Server Check

```json
{
  "check": {
    "name": "SQL Server Check",
    "checkType": {"code": "sqlCheck"},
    "config": "{\"dbHost\":\"db.example.org\",\"dbPort\": \"3306\", \"dbUser\":\"basicUser\",\"dbPassword\":\"basicPassword\", \"dbName\": \"mydb\", \"dbQuery\": \"select 1\", \"checkOperator\": \"lt\", \"checkResult\": 2}"
  }
}
```

Code: `sqlCheck`

The SQL Server Check allows you not only to confirm that a Microsoft SQL Server database is up and running but also allows you to run a query and test the result value. This can be useful for doing a slow query check or just making sure something isnt growing out of control.

Parameter | Requirement | Description
--------- | ----------- | -----------
dbHost    | Yes         | The hostname / ipaddress of the sql database
dbPort    | Yes         | The SQL Port (defaults to 1433)
dbUser    | Yes         | The Database username
dbPassword | Yes        | The Database password (remember this gets encrypted)
dbName    | Yes         | The database name you would like to connect to
checkOperator  | No     | Can be set to lt (less than), gt (greater than), equal (Equal to) for comparison
checkResult | No        | Numerical value to compare the check result against. 

<aside class="notice">More often than not you will not want to directly connect to your sql database on the open web. There are some options here. One is to use ssh tunneling which can be configured via adding some additional parameters to the config json (See the section on SSH Checks). Another option is to run our agent with an upgraded plan where the check can run from within a firewall.</aside>

### PostgreSQL Check

```json
{
  "check": {
    "name": "PostgerSQL Check",
    "checkType": {"code": "postgresCheck"},
    "config": "{\"dbHost\":\"db.example.org\",\"dbPort\": \"3306\", \"dbUser\":\"basicUser\",\"dbPassword\":\"basicPassword\", \"dbName\": \"mydb\", \"dbQuery\": \"select 1\", \"checkOperator\": \"lt\", \"checkResult\": 2}"
  }
}
```

Code: `postgresCheck`

The Postgres Check allows you not only to confirm that a mysql database is up and running but also allows you to run a query and test the result value. This can be useful for doing a slow query check or just making sure something isnt growing out of control.

Parameter | Requirement | Description
--------- | ----------- | -----------
dbHost    | Yes         | The hostname / ipaddress of the postgres database
dbPort    | Yes         | The Postgres Port (defaults to 5432)
dbUser    | Yes         | The Database username
dbPassword | Yes        | The Database password (remember this gets encrypted)
dbName    | Yes         | The database name you would like to connect to
checkOperator  | No     | Can be set to lt (less than), gt (greater than), equal (Equal to) for comparison
checkResult | No        | Numerical value to compare the check result against. 

<aside class="notice">More often than not you will not want to directly connect to your postgres database on the open web. There are some options here. One is to use ssh tunneling which can be configured via adding some additional parameters to the config json (See the section on SSH Checks). Another option is to run our agent with an upgraded plan where the check can run from within a firewall.</aside>


### Socket Check

```json
{
  "check": {
    "name": "Socket Check",
    "checkType": {"code": "socketCheck"},
    "config": "{\"host\":\"test.example.org\",\"port\": \"3306\", \"send\":\"blah\",\"responseMatch\":\"OK\"}"
  }
}
```

Code: `socketCheck`

With a socket check you can confirm that certain TCP based services  are up and running within your environment. This can configured to both do an initial send upon connect and a comparison of the response made.

Parameter | Requirement | Description
--------- | ----------- | -----------
host      | Yes         | The hostname / ipaddress of the socket server
port      | Yes         | The port we want to connect to
send      | No          | A String you might want to send upon connect
responseMatch | No      | if you wish to test for a response match enter a string here

### Elastic Search Check

```json
{
  "check": {
    "name": "Socket Check",
    "checkType": {"code": "elasticSearchCheck"},
    "config": "{\"esHost\":\"test.example.org\",\"esPort\": \"9200\"}"
  }
}
```

Code: `elasticSearchCheck`

The elastic search check is capable of connecting to your elastic search cluster / node and verifying its cluster health. It will also grab statistical information such as document size, capacity, and cpu usage for easy reference.

Parameter | Requirement | Description
--------- | ----------- | -----------
esHost      | Yes         | The hostname / ipaddress of the ElasticSearch server
esPort      | Yes         | The http based port we want to connect to

<aside class="notice">More often than not you will not want to directly connect to your ellastic database on the open web due to the lack of authentication. There are some options here. One is to use ssh tunneling which can be configured via adding some additional parameters to the config json (See the section on SSH Checks). Another option is to run our agent with an upgraded plan where the check can run from within a firewall.</aside>

## SSH Tunneling

SSH Tunneling options allow the different check types to tunnel into a host and perform checks relative to that host. The SSH Tunnel can use your account generated public/private key pair or a simple ssh password (however we strongly recommend the key pair).

To turn on ssh tunneling on a check some parameters can be added to any check type config as seen earlier in the Check Types section.

```json
{
  "check": {
    "name": "Socket Check",
    "checkType": {"code": "elasticSearchCheck"},
    "config": "{\"esHost\":\"test.example.org\",\"esPort\": \"9200\", \"tunnelOn\": \"on\", \"sshHost\": \"example.org\", \"sshPort\": 22, \"sshUser\": \"happyapps\"}"
  }
}
```

Parameter | Requirement | Description
--------- | ----------- | -----------
tunnelOn  | Yes         | Set to "on" to turn on tunneling
sshHost   | Yes         | The hostname or ip address of the tunnel destination
sshPort   | No          | Defaults to port 22
sshUser   | Yes         | The SSH Username on the target host we want to login as
sshPassword | No        | Used if not using key based authentication

<aside class="notice">A Note on Security. The config map for connecting to an ssh destination is heavily encrypted within our systems. The account keypairs are rsa-2048 bit encrypted as well and secure. In the event one becomes uncomfortable using this keypair it can always be cleared and reset in the account settings. If SSH is not an approach you want to take, an agent provides all the same functionality without the concern.</aside>

## Mute a Check


```shell
curl -XPUT "https://api.happyapps.io/api/checks/1/mute" \
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

This endpoint can be used to toggle the mute state of a Check.

## Delete a Check

```shell
curl -XDELETE "https://api.happyapps.io/api/checks/1" \
  -H "Authorization: BEARER access_token"
```

> The above command returns JSON Structured like this:

```json
{
  "success": true
}
```

A Deleted check can be fetched optionally from the GET api for sync verification but can no longer be used or updated.


### HTTP Request

`PUT https://api.happyapps.io/api/checks/:id/mute`

### JSON Parameters

Parameter | Description
--------- | -----------
enabled | Set this to true or false depending on if you want to mute or unmute a check.
