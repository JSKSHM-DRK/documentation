### Producer API
The producer sends messages to Kafka topics.
- `POST /produce` accepts a topic and a message.
- Example:
  ```json
  {
    "topic": "test",
    "message": "Hello Kafka"
  }
## Consumer API
The consumer reads messages from Kafka.
### Endpoint:
```bash
GET /consume?topic=test
```

### Query Parameters:

```topic``` (required): Name of the topic to consume messages from.

### Response:
```
[
  {
    "message": "Hello Kafka"
  },
  ...
]
```


## Admin API
(Admin endpoints can be added for future use)
Possible features:
- Create/Delete topics
- View partitions and topic metadata
- Monitor broker status



