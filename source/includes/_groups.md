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
}
```