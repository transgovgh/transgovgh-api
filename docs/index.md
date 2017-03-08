# Welcome to Transgov Ghana Api documantation

For full information about Transgov visit [www.transgovgh.org](http://transgovgh.org).

Quick notes

This section describes the usage of the Transgov Mobile API. To get started. To fully implement the mobile API, you must understand following standards.

Official API for the Transgov Mobile Applications

### Base URLs

 - To test the api on stage server, use: ``http://stage.transgovgh.org/api/v1.0/``
 - To use the live or production api, use: ``http://transgovgh.org/api/v1.0/`` as your base URL. The base url must preceed all endpoints used to interact with the API server.


### API Responses

Generally, all API responses are returned in the standard `JSON` format.

### Good Response

The standard HTTP response code which occures when data is submitted or data is fetched begins with `2` e.g. , `200 Ok`, `201 Created`, You will have a standard json response with a format:

    {
         "status_code": 200,
         "message": "You have fetched all the data",
         "results": [
         ....................
         ]
    }

The ``status_code`` in the response body describes the internal status code which describes the `message` of the error. The details describe the exact error that occurred and the results brings out the response of the request,


### Error Codes

Apart from the standard HTTP errors, there are errors codes which can be returned when something goes wrong. When an error with HTTP error code begins with `4` e.g. `400 (Bad Request)`, `401 (UnAuthorized)` You will have a standard json response with a format:

    {
         "status_code": 400,
         "message": "Bad request. Data was not saved. Please check the fields and data you are submitting"
    }

The ``status_code`` in the response body describes the internal status code which describes the `message` of the error. The details describe the exact error that occurred.

### Owner

Transgov Ghana Limited.

### Developer

Kennedy Anyinatoe.
