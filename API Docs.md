# API Docs

### HTTP Basic Auth Test

username: driverId

password: secretId

```
GET /auth_test

eg: GET http://driver123:secret234@localhost:8080/auth_test
```

keep the basic auth anywhere.

return body

```
HTTP 200 {status: "ok"} # if you login correctly
HTTP 401 {status: "failed"} # if auth fauled
```

### List Key Permission

```
HTTP BASIC AUTH REQUIRED
GET /permission
```

return

```
HTTP 401 {status: "failed"} # if auth fauled
HTTP 200 
{
  status: "ok",
  permissions: [0, 1] # 0 for Location, 1 for Security Options(Speed, Airbags and Seatbelt)
}
```

### Event WebSocket

```
WEBSOCKET /event
send:
{
  driver_id: string,
  secret_id: string,
  filters: [
  	{name: "seatbelt", range: [0, 1, 2, 3]},
  	{name: "inhibited", range: ["airbag", "ESC"]},
  	{name: "location", range: [lat, lon, lat, lon, ...]},
  	{name: "speed", limit: 120},
  	{name: "crash"}
  ]
}

return:
{
  message: "xxxxxxx"
}
```

