# Tech Stack
* .gitignore
* README.md

## TODOs
* License
* docker-compose file 
* Dockerfile
* Exception Handler
* Logging
* Caching
* Pagination
* Filtering
* Ordering
* Versioning
* Result Message Formats

## Sources
* https://profil-software.com/blog/development/10-things-you-need-know-effectively-use-django-rest-framework/
* https://stackoverflow.blog/2020/03/02/best-practices-for-rest-api-design/
* https://learn.microsoft.com/en-us/azure/architecture/best-practices/api-design
* https://document360.com/blog/api-design-best-practices/
* https://josipmisko.com/posts/rest-api-best-practices
* https://www.softkraft.co/how-to-build-rest-api-with-django/

* https://medium.com/analytics-vidhya/10-must-have-tips-of-django-rest-framework-to-increase-your-coding-efficiency-87ebea0e0099
* 

## Best Practices
* Client-Server Architecture
* Ensure that the API scales
* Use an international design standard The OpenAPI v3
* Cacheable
* Stateless
* Use Nouns Instead of Verbs in Endpoints -> https://mysite.com/posts not https://mysite.com/createPost
* Don't use POST: /articles/createNewArticle/ Do use POST: /articles/
* Name Collections with Plural Nouns -> So, instead of https://mysite.com/post/123, it should be https://mysite.com/posts/123, GET /cars/123, POST /cars, GET /cars
* Use Status Codes in Error Handling -> Informational Responses, Redirects, Client-side errors, Server-side errors
* Use Nesting on Endpoints to Show Relationships -> https://mysite.com/posts/postId/comments, You should avoid nesting that is more than 3 levels deep as this can make the API less elegant and readable
* Use Filtering, Sorting, and Pagination to Retrieve the Data Requested -> https://mysite.com/posts?sortBy=createdAt&sortOrder=desc&limit=10&offset=0
* Use SSL for Security -> https://mysite.com/posts
* Be Clear with Versioning -> https://mysite.com/v2 for version 2
* RETURN ERROR DETAILS IN THE RESPONSE BODY -> 
    {
    "error": "Invalid payoad.",
    "detail": {
        "surname": "This field is required."
    }
}
* Provide Accurate API Documentation -> 
  * The documentation should contain:
    * relevant endpoints of the API
    * example requests of the endpoints
    * implementation in several programming languages
    * messages listed for different errors with their status codes

Custom response model
seeder and data
Response message with status codes { ‘status’:’success|error’, ‘data’:{ 'result':{} || [] , '' }, #one level ‘meta’:{} #any meta information that you want to pass } 200 OK — Success — GET/PUT — return resource/status message 201 Created — Success — POST — provide status message or return newly created object 204 No Content — Success — DELETE 304 Unchanged — Redirect — ALL — Indicates no changes since last request 400 Bad Request — Failure — GET/PUT/POST — invalid request, return error messages 401 Unauthorized — Failure — ALL — missing credentials/Authentication required 403 Forbidden — Failure — ALL — restricted content 404 Not Found — Failure — Resource not found 405 Method Not Allowed Failure — Failure — ALL — An invalid HTTP method was attempted

Versioning Your APIs:
Implement API versioning from the beginning to ensure backward compatibility as your API evolves. DRF provides easy-to-use tools for versioning, allowing you to handle changes gracefully.
Serialization for Data Representation:
Proper serialization is crucial for transforming complex Python data types into JSON or other formats. Use DRF serializers to convert data and control the output efficiently.
Using DRF’s Class-Based Views (CBVs):
Opt for DRF’s CBVs to structure your views logically and make use of built-in mixins to handle common tasks like pagination, filtering, and authentication.
Authentication and Permissions:
Secure your APIs by integrating authentication methods such as token-based or OAuth2 authentication. Additionally, fine-tune permissions to control access to specific endpoints.
Throttling and Rate Limiting:
Implement throttling and rate limiting to prevent abuse and ensure fair usage of your API. DRF offers simple ways to set these limits based on user or IP address.
Pagination for Large Data Sets:
Use DRF’s pagination classes to break down large datasets into manageable chunks, ensuring optimal performance and user experience.
Validation and Error Handling:
DRF provides comprehensive validation tools to ensure data integrity. Handle errors gracefully and provide meaningful error responses to API consumers.
Nested Serializers and Related Data:
When dealing with complex data structures and related models, use nested serializers to represent the data in a structured manner and facilitate data retrieval.
Optimizing Database Queries:
Avoid the N+1 query problem by using DRF’s queryset optimization techniques like select_related and prefetch_related to minimize database queries.
Caching Responses:
Cache frequently requested API responses to improve performance and reduce the load on your server. DRF supports various caching strategies that can be easily integrated.
Unit Testing for API Endpoints:
Write comprehensive unit tests using DRF’s testing tools to validate the functionality of your API endpoints. Test-driven development (TDD) ensures a robust and bug-free API.
Documentation with Swagger and API Docs:
Leverage DRF’s support for API documentation tools like Swagger and API Docs to provide clear and up-to-date documentation for your API consumers.

## Examples
USE RESOURCE NESTING
/users // list all users
/users/123 // specific user
/users/123/orders // list of orders that belong to a specific user
/users/123/orders/0001 // specific order of a specific users order list