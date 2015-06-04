# Push Checks

A Push Check is a check type that is not run by any of our happy apps check servers nor an agent. Rather it acts as a web hook where the user is responsible for submitting status updates to happy apps about the check. These status updates need to be regularly submitted and consistent with the checks configured time interval. If a check has not been heard from for more than 2x the check interval time it is marked as a failed check and an incident is raised.

To create a Push Check please check the Checks API or create a Push Check in the UI.

## Submitting a Check Status

```shell
curl -XPOST https://api.happyapps.io/api/push?apiKey=INSERT_KEY_HERE -H 'Content-Type: application/json' \
--data '{
  "success":true,
  "message": "any comment goes here",
  "startDate": "2015-05-01T12:35:14Z",
  "endDate": "2015-05-01T12:35:14Z"
  }'
```

> The above will return JSON in the format of

```json
{"success":true}
```

> If you are pushing updates to quickly the response will be a 429 with the following payload

```json
{"success":false,"msg":"Pushed too quickly, please wait 54004ms before sending again."}
```

### HTTP Request

`POST https://api.happyapps.io/api/push?apiKey=INSERT_KEY_HERE`

### JSON Parameters

Parameter | Default | Description
--------- | ------- | -----------
success   | false   | Set wether or not the check passed
startDate | NOW()   | The start time of the check run (optional)
endDate   | NOW()   | The end time of the  check run time (if specified with start date the response time metric will be accurately represented)
message   | null    | An optional string message that will show in the check history for the particular check run

<aside class="notice">Don't forget to Push it real good!</aside>
