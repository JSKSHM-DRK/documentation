## Development Setup
```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
uvicorn app:app --reload
```

## Code Style Guidelines
- Use Black and isort for formatting.

- Follow [PEP8](https://peps.python.org/pep-0008/)
* * *
## Testing
- Run unit tests using:
  ```bash
  pytest tests/
  ```
- Mock Kafka for integration testing if needed.
***
## Pull Request Process
- Fork → Branch → Commit → Pull Request

- Run tests before submitting PR.

- Follow the commit message conventions.
***

  



