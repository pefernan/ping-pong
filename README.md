# Modified Ping Pong example

## Testing

Create an instance of the ping process:

```sh
curl -X 'POST' \
  'http://localhost:8080/ping_message' \
  -H 'accept: */*' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

NOTE: This process instance then waits in the catch message event node.

Create an instance of the pong process:

```sh
curl -X 'POST' \
  'http://localhost:8080/pong_message' \
  -H 'accept: */*' \
  -H 'Content-Type: application/json' \
  -d '{
  "message": "hi"
}'
```

Signal the pong process:
```sh
curl -X 'POST' \
  'http://localhost:8080/pong_message/UUID/end' \
  -H 'accept: application/json' \
  -d ''
```
