# Tech Stack
* Programming Lang: Python
* Web Framework: Django
* REST Framework: Django Rest Framework -> https://www.django-rest-framework.org/
* Database: PostgreSQL
* Web Server: NGINX (Serve Static Files)
* Containerization: Docker
* Version Control: Git
* Version Control Hosting: GitHub
* API Documentation: Self Describing (Browsable) APIs Documentation, Swagger, Redoc, Postman Collection -> https://www.django-rest-framework.org/topics/documenting-your-api/
* Authentication & Authorization: JWT -> https://jwt.io/
* Package Installer -> PIP
* Dependency Management -> Virtualenv
* Dependencies -> requirements.txt
* Views -> https://www.django-rest-framework.org/api-guide/views/, Function-Based Views, Class Based (APIView, ,Generic Views, Mixins)
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
* Permission Authentication
* Filtering
* Authentication -> Basic Authentication, Session Authentication, Token Authentication, JWT Authentication, RemoteUserAuthentication, SessionAuthentication, CustomAuthentication
* Ordering
* Versioning
* Result Message Formats
* TDD -> https://realpython.com/test-driven-development-of-a-django-restful-api/

## Sources
* https://hevodata.com/learn/rest-api-best-practices/
* https://swagger.io/resources/articles/best-practices-in-api-design/
* https://medium.com/deliveryherotechhub/rest-api-tasar%C4%B1m%C4%B1-ve-best-practices-37ea7041b27
* https://dev.to/ksaaskil/tips-for-building-a-clean-rest-api-in-django-2pae
* https://django-best-practices.readthedocs.io/en/latest/code.html
* https://docs.djangoproject.com/en/dev/internals/contributing/writing-code/coding-style/
* https://www.toptal.com/django/django-top-10-mistakes
* https://learning.oreilly.com/library/view/django-design-patterns/9781788831345/08d91bf0-986c-415c-9120-1b7e908d7aec.xhtml
* https://cheatsheetseries.owasp.org/cheatsheets/Django_REST_Framework_Cheat_Sheet.html
* https://profil-software.com/blog/development/10-things-you-need-know-effectively-use-django-rest-framework/
* https://stackoverflow.blog/2020/03/02/best-practices-for-rest-api-design/
* https://learn.microsoft.com/en-us/azure/architecture/best-practices/api-design
* https://document360.com/blog/api-design-best-practices/
* https://josipmisko.com/posts/rest-api-best-practices
* https://www.softkraft.co/how-to-build-rest-api-with-django/
* https://www.mindbowser.com/best-practices-for-rest-api-design/

* https://github.com/saqibur/django-project-structure
* https://github.com/HackSoftware/Django-Styleguide
* https://github.com/Joabsonlg/django-api-template
* https://gist.github.com/TechRancher/6440451a05797d8e1c61642347ca6b69
* https://github.com/PragatiVerma18/Django-For-APIs/blob/master/Best-Practices-In-REST.md
* https://github.com/cunhaax/django-rest-template
* https://github.com/weynelucas/drf-project-template
* https://github.com/rephus/django-rest-template
* https://github.com/xionglilong/django-rest-framework-template
* https://github.com/asapdevelopers/django-rest-framework-template
* https://github.com/Keats/django-drf-template
* https://github.com/bitnob/django-rest-template
* https://github.com/juanbenitezdev/django-rest-framework-crud
* https://github.com/ArchTaqi/django-rest-api
* https://github.com/ukjin1192/django-rest-framework-example

* https://medium.com/@ebin7joseph/django-rest-framework-authentication-with-jwt-8687494509d8
* https://blog.logrocket.com/django-rest-framework-create-api/
* https://python.plainenglish.io/building-in-the-update-functionality-with-django-rest-framework-60c3f0436927
* https://levelup.gitconnected.com/restful-django-django-rest-framework-8b62bed31dd8
* https://medium.com/analytics-vidhya/10-must-have-tips-of-django-rest-framework-to-increase-your-coding-efficiency-87ebea0e0099
* https://www.rootstrap.com/blog/django-best-practices-and-beginner-tips

## Samples
* https://djangostars.com/blog/rest-apis-django-development/
* https://medium.com/crowdbotics/how-to-write-an-api-in-3-lines-of-code-with-django-rest-framework-59b0971edfa4
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

Tests should cover all API endpoints
Leverage DRF's APITestCase and be sure to use mock to mock external API calls
Check that valid data is returned for 201 or 200 responses
Be sure to include tests that cover all possible error conditions
Make sure the proper error codes/messages are being returned for 4xx responses
Add unit tests for any complicated functions wherever appropriate
Remember, there's no such thing as "too many tests"

try:
    user = User.objects.create(username=email, password=password)
except IntegrityError:
    return Response(
        {'detail': 'User with that email already exists.'},
        status=status.HTTP_409_CONFLICT)

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

class CartItemViews(APIView):
    def post(self, request):
        serializer = CartItemSerializer(data=request.data)
        if serializer.is_valid():
            serializer.save()
            return Response({"status": "success", "data": serializer.data}, status=status.HTTP_200_OK)
        else:
            return Response({"status": "error", "data": serializer.errors}, status=status.HTTP_400_BAD_REQUEST)

class CartItemViews(APIView):

    def get(self, request, id=None):
        if id:
            item = CartItem.objects.get(id=id)
            serializer = CartItemSerializer(item)
            return Response({"status": "success", "data": serializer.data}, status=status.HTTP_200_OK)

        items = CartItem.objects.all()
        serializer = CartItemSerializer(items, many=True)
        return Response({"status": "success", "data": serializer.data}, status=status.HTTP_200_OK)


myproject_website/
├── commands/
├── db_backups/
├── mockups/
├── src/
│   └── django-myproject/
│       ├── externals/
│       │   ├── apps/
│       │   │   └── README.md
│       │   └── libs/
│       │       └── README.md
│       ├── locale/
│       ├── media/
│       ├── myproject/
│       │   ├── apps/
│       │   │   ├── core/
│       │   │   │   ├── __init__.py
│       │   │   │   └── versioning.py
│       │   │   └── __init__.py
│       │   ├── settings/
│       │   │   ├── __init__.py
│       │   │   ├── _base.py
│       │   │   ├── dev.py
│       │   │   ├── production.py
│       │   │   ├── sample_secrets.json
│       │   │   ├── secrets.json
│       │   │   ├── staging.py
│       │   │   └── test.py
│       │   ├── site_static/
│       │   │   └── site/
│       │   │  django-admin.py startproject myproject     ├── css/
│       │   │       │   └── style.css
│       │   │       ├── img/
│       │   │       │   ├── favicon-16x16.png
│       │   │       │   ├── favicon-32x32.png
│       │   │       │   └── favicon.ico
│       │   │       ├── js/
│       │   │       │   └── main.js
│       │   │       └── scss/
│       │   │           └── style.scss
│       │   ├── templates/
│       │   │   ├── base.html
│       │   │   └── index.html
│       │   ├── __init__.py
│       │   ├── urls.py
│       │   └── wsgi.py
│       ├── requirements/
│       │   ├── _base.txt
│       │   ├── dev.txt
│       │   ├── production.txt
│       │   ├── staging.txt
│       │   └── test.txt
│       ├── static/
│       ├── LICENSE
│       └── manage.py
└── env/