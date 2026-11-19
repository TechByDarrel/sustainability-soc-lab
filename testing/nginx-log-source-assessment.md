# Nginx Log Source Assessment

## Environment
- Operating system: Ubuntu 26.04.1 LTS
- Platform: WSL 2
- Web server: Nginx 1.28.3
- Service status: Active (running)
- Service startup: Enabled

## Log Files

| Log | Location | Status |
|---|---|---|
| Access log | /var/log/nginx/access.log | Verified |
| Error log | /var/log/nginx/error.log | Verified |

## Local Request Test

A local HTTP HEAD request was sent to:

- Address: 127.0.0.1
- Path: /
- HTTP response: 200 OK
- Client: curl/8.18.0

The access log recorded the request with:
- Source address: 127.0.0.1
- Method: HEAD
- Requested path: /
- Status code: 200

## Error Log Observation

The error log contained an Nginx startup notice.

No application error was observed during this test.

## Limitations
- Only normal local web traffic has been tested.
- No suspicious web activity has been generated or detected.
- The server is being used as a local lab source, not an internet-facing service.

## Conclusion

Nginx is installed, running and generating accessible web-server logs.

The source is suitable for subsequent web-event collection and detection testing.
