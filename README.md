# API documentation and specification for SOA grupp 2

The following APIS should exist in this repo:

- mock Ladok
- mock Epok
- mock studentITS
- mock Canvas?
- student-service, internal
- examination-service, internal
- combined services, external (for frontend web interface)


These follow the OpenAPI specification version 3 (Swagger).


Recommended toolset for working with these files is [Stoplight Studio](https://github.com/stoplightio/studio) or at [Stoplight.io](https://stoplight.io/studio). The .yml files can be opened in programs such as Postman and then run automated tests agains an API implementation.


There are numerous tools to autogenerate documentation from these API specifications, they are also useful for running tests with and providing the configuration for test servers - as well as just being a centeral source of truth to write the API implementations for.



# Some general API guidelines
The following are the practices best followed in the design of these specifications.

## Endpoint naming
Use plural endpoints names. So a request is made to `myserver.com/api/v1/users` (with an 's'). Don't use verbs in endpoints - instead use the HTTP verbs GET, PUT(update), DELETE and POST.

## Resource naming
Name the resources which are served in their singular form so an entity served would be a 'user' for example. Also use nouns obviously, not verbs.

## HTTP status error codes
Make sure error codes are meaningful.

    400 Bad Request – This means that client-side input fails validation.
    401 Unauthorized – This means the user isn’t not authorized to access a resource. It usually returns when the user isn’t authenticated.
    403 Forbidden – This means the user is authenticated, but it’s not allowed to access a resource.
    404 Not Found – This indicates that a resource is not found.
    500 Internal server error – This is a generic server error. It probably shouldn’t be thrown explicitly.
    502 Bad Gateway – This indicates an invalid response from an upstream server.
    503 Service Unavailable – This indicates that something unexpected happened on server side (It can be anything like server overload, some parts of the system failed, etc.).

## Versioning
Make sure that the api has a versioning scheme in the URL 'v1', 'v2' etc.


