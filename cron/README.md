# Keda Cron Trigger

Cron trigger which scales the container/workload based on the cron expression of a particular region/location.

## Example

```
triggers:
- type: cron
  metadata:
    # Required
    timezone: Asia/Kolkata  # The acceptable values would be a value from the IANA Time Zone Database.
    start: 0 6 * * *        # At 6:00 AM
    end: 0 20 * * *         # At 8:00 PM
    desiredReplicas: "10"
```

We can override the docker entrypoint of a container through the keda process like below:

```
containers:
    - name: nginx-job
      image: nginx
      imagePullPolicy: Always
      command: ["echo","some Job Running"]
```

For more details refer to the official [documentation](https://keda.sh/docs/2.13/scalers/cron/) for cron triggers.