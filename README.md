# execute-postman-monitor

Executes an existing Postman monitor, given its id.


## Usage
Example of trigger on pull request.

```yaml
name: Execute Postman Monitor
on:
  pull_request:
jobs:
  sync-with-postman-api:
    runs-on: ubuntu-latest
    steps:
      - name: Execute Postman Monitor
        id: executeMonitor
        uses: davidespihernandez/execute-postman-monitor@v1
        with:
          postman-api-key: ${{ secrets.POSTMAN_API_KEY }}
          monitor-id: ${{ vars.MONITOR_ID }}
```

For the previous example to work you need to define:
- An environment variable `MONITOR_ID` containing the monitor id to be executed.
- A secret called `POSTMAN_API_KEY` containing the Postman API key with admin permission on the monitor that is going to be executed.

## License

MIT

