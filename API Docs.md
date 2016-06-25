# API Docs

### HTTP Basic Auth

username: driverId

password: secretId

```
GET /auth_test

eg: GET http://driver123:secret234@localhost:8080/auth_test
```

keep the basic auth anywhere.

```
{status: "ok"} # if you login correctly
{status: "failed"} # if auth fauled
```



### List Key Permission

```
AUTH REQUIRED
GET /permission
```

