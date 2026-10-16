# Employee Management API Testing with Postman

## Project Overview

This project demonstrates REST API testing using Postman against the
GoRest public API. GoRest exposes **user records**, which are used here
as employee-like sample records for CRUD testing. This is a practice API
project, not a production employee management system.

## Tools and Technologies

-   Postman
-   REST API methods: GET, POST, PUT, DELETE
-   JavaScript assertions in Postman Post-response scripts
-   JSON request and response validation
-   Collection Runner

## API Base URL

`https://gorest.in/public/v2`

## Test Coverage

  -------------------------------------------------------------------------------------
  Test Case      Scenario       Method               Expected/Observed   Reported
                                                     Status              Result
  -------------- -------------- -------------------- ------------------- --------------
  TC01           Retrieve all   GET `/users`         200 OK              Passed
                 user records                                            

  TC02           Create a user  POST `/users`        201 Created         Passed
                 record                                                  

  TC03           Update a user  PUT `/users/1023`    200 OK              Passed
                 record                                                  

  TC04           Delete a user  DELETE `/users/1023` 204 No Content      Passed
                 record                                                  

  TC05           Delete using   DELETE               400 or 404;         Passed
                 an invalid ID  `/users/999999999`   observed 404        
  -------------------------------------------------------------------------------------

The project owner reported that all five requests passed in Postman's
Collection Runner. Re-run the collection before publishing a new
execution report, since public API data and behavior may change.

## Assertions Covered

-   HTTP status-code validation
-   Response JSON structure and required fields
-   Created record ID presence
-   Name and email field validation
-   Updated field validation
-   Empty body validation for a 204 response
-   Negative testing for an invalid/nonexistent ID

## How to Run

1.  Import `Employee_Management_API_Testing.postman_collection.json`
    into Postman.
2.  Configure the GoRest bearer token using a local Postman environment
    or another private variable.
3.  Confirm that no real token is hardcoded in the exported collection.
4.  Open the collection and choose **Run collection**.
5.  Run the requests in the intended order.
6.  Review actual response codes, assertion results, and failures in
    Collection Runner.

## Authentication and Secret Handling

Some GoRest endpoints require a bearer token. Obtain your own token from
the API provider and store it locally in Postman. Do not commit access
tokens to GitHub, screenshots, README files, or public collection
exports.

Before sharing the collection, inspect authorization settings and remove
or replace any secret value with a variable such as `{{gorest_token}}`.

## Project Files

-   `Employee_Management_API_Testing.postman_collection.json` --- export
    from Postman
-   `Employee_Management_API_Test_Cases.xlsx` --- test-case report
-   `README.md` --- project documentation

## Limitations

-   GoRest is a public API for user records, not a dedicated
    employee-management service.
-   Public API data may change; a record created in one run may not be
    available later.
-   Reported test results describe the observed practice run and are not
    a guarantee of future API behavior.
-   The invalid-ID test currently accepts either HTTP 400 or 404 as a
    client error; the observed response was HTTP 404.

## Author

Add your name and GitHub profile here before publishing.
