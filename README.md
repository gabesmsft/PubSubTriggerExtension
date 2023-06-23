## Functions

| Function name | Dapr component type(s) | HTTP method (if applicable) | HTTP route (if applicable) | Description |
| ------------- | ---------------------- | --------------------------- | -------------------------- | ----------- |
| HttpTriggerWithDaprPubSubExtensionOutput | Pubsub output | POST | /api/mypubsubpublisher | Publishes a message to the pubsub |
| DaprPubSubExtensionTrigger | Pubsub trigger | | | Is expected to trigger when a message is published to the pubsub |

## Local testing

To run the application locally. Change to the *project* directory (not solution directory), and then run the following command:
```
dapr run --app-id functionapp1 --dapr-http-port 3500 --app-port 3001 --components-path ./components -- func host start 
```

To publish a message to the pubsub:

```
curl -H "Content-Type: application/json" -X POST http://localhost:7071/api/mypubsubpublisher -d "{"hello": "world"}"
```
