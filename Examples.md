## Basic Examples
**Produce a message:**
``` bash
curl -X POST http://localhost:8000/produce \
  -H "Content-Type: application/json" \
  -d '{"topic":"test", "message":"Kafka test"}'

```

**Consume messages:**
```bash 
curl http://localhost:8000/consume?topic=test
```

## Real World Scenarios
- Payment transaction pipeline
- User activity tracking
- Log aggregation from microservices

## Integration with Other Systems

- Use Kafka Connect to sync with:

	- PostgreSQL / MySQL

	- MongoDB

	- Elasticsearch

## Batch Processing
- Read messages in bulk.

- Write to data warehouse or batch DB jobs.


## Stream Processing
- Real-time transformations using:

	- Faust (Python)

	- Kafka Streams (Java)