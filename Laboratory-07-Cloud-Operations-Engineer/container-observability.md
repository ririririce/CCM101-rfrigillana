### 404 Error Log

```text
172.17.0.1 - - [13/Oct/2026:13:36:15 +0000] "GET /hidden-admin-page HTTP/1.1" 404 153 "-" "curl/8.5.0" "-"
```

### Why Application Logs Are Important?

Application logs help me see what went wrong when someone uses a website. They make it easier to find and fix problems by showing which pages were accessed and whether the requests were successful or had errors.

---

## Real-Time Container Metrics

I used the `docker stats` command to check how much CPU and memory my `client-website` container was using.

- **Memory Usage:** 2.734 MiB
- **CPU Usage:** 0.00%
- **Network I/O:** 2.75 kB received / 2.35 kB sent

Based on the results, the container was using very little CPU and memory at the time of monitoring.

