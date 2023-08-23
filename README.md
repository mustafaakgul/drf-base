* .gitignore
* README.md

## TODOs
* License


## Notes
docker-compose file
Dockerfile
Response Status
Response message with status codes { ‘status’:’success|error’, ‘data’:{ 'result':{} || [] , '' }, #one level ‘meta’:{} #any meta information that you want to pass } 200 OK — Success — GET/PUT — return resource/status message 201 Created — Success — POST — provide status message or return newly created object 204 No Content — Success — DELETE 304 Unchanged — Redirect — ALL — Indicates no changes since last request 400 Bad Request — Failure — GET/PUT/POST — invalid request, return error messages 401 Unauthorized — Failure — ALL — missing credentials/Authentication required 403 Forbidden — Failure — ALL — restricted content 404 Not Found — Failure — Resource not found 405 Method Not Allowed Failure — Failure — ALL — An invalid HTTP method was attempted