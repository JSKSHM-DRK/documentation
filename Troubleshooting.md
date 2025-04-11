## Common Issues
| **Issue**                     | **Solution**                                       |
|------------------------------|----------------------------------------------------|
| Kafka won't start            | Check Docker logs and port availability            |
| Can't connect to Kafka       | Verify Kafka hostname, port, and Docker network    |
| Messages not consumed        | Confirm topic name, group ID, and offset settings  |
| Consumer times out           | Check if there are any new messages in the topic   |
| Producer fails silently      | Ensure topic exists and Kafka is reachable         |
| JSON decode errors           | Validate message structure before sending          |
| Connection refused error     | Confirm Kafka broker is running and reachable      |
| Docker containers not linking| Use correct container names or `--network` config  |

* * *
## Debugging Tips
- Use Kafka CLI tools:
```
kafka-topics.sh --list --bootstrap-server localhost:9092
kafka-console-consumer.sh --topic test --from-beginning --bootstrap-server localhost:9092

```
- Enable logging in `logging.conf`.

  
* * *
## FAQ
**Q: Can I use this without Docker?**  
Yes. You can install Kafka and Zookeeper manually on your system and update the `bootstrap_servers` configuration in your code to point to `localhost:9092` or the appropriate broker address.

---

**Q: Does it support Avro or Protobuf serialization?**  
Currently, JSON serialization is used by default. However, you can extend the project to support **Avro** using `fastavro` or **Protobuf** using `protobuf` libraries. You'll also need a schema registry if using Avro in a real-world setup.

---

**Q: How can I consume messages continuously instead of making a GET request each time?**  
You can run a background thread or task that starts a persistent consumer loop, or you can use a Kafka client that supports event-driven consumers such as `confluent-kafka`.

---

**Q: What happens if Kafka is down when I try to send a message?**  
The producer will raise an exception. You should implement retry logic and error handling to gracefully handle such cases.

---

**Q: How do I handle message order?**  
Kafka preserves order **within a partition**. To maintain strict ordering, ensure all related messages are sent to the same partition using a consistent key.

---

**Q: Is there any message size limit?**  
Yes. The default max message size is **1MB**. This can be increased using Kafka broker and producer configurations like `message.max.bytes` and `max.request.size`.

---

**Q: Can I secure Kafka communication?**  
Yes. You can enable SSL/TLS for encryption and SASL for authentication. Update the Kafka server and client configurations accordingly to include keystore and truststore credentials.

---

**Q: How can I delete a topic using this setup?**  
Admin API functionality for deleting or creating topics is not included by default but can be added using `kafka.admin` in `kafka-python`.

---

**Q: Why am I getting duplicate messages?**  
This can happen if the consumer commits offsets before processing is complete or if the producer retries without idempotence. Enable `enable.idempotence=True` in producer settings to mitigate this.

---

**Q: Can I deploy this project to the cloud?**  
Yes! This FastAPI + Kafka setup can be containerized using Docker and deployed on:
- AWS EC2 / ECS / EKS
- Google Cloud Run / GKE
- Azure Kubernetes or App Services



