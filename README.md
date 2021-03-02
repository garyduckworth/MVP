SUMMARY
=======

MVP Math is a RESTful API used for evaluating BEDMAS calculations via GET and POST requests

For example, API can be used to evaluate expressions such as "2*(7-3)"

The following criteria is met with the MVP Math API:

1. Expressions can perform the following:

   * Additions
   * Subtractions
   * Multiplications
   * Divisions

2. Multiple operations can be chained together

3. BEDMAS order of operation will be applied to expressions

4. Calculations will use MVP Math algorithm, If execution fails API will use legacy algorithms.

NOTE: MVP Math replaces legacy Saas product


EXECUTION
=========

Execution can tested through the web application detailed below or through the use of Swagger

For example, Swagger can be invoked during execution by adding "/swagger" to the base URL address (See Examples)

Testing can also be performed directly on the API itself by setting it as the startup project, running the application, and entering the query examples below in address bar. This will then show the result in the browser. Executions are limited to 10 seconds with a maximum of 10,000 requests per day.


QUERY PARAMETERS
================

expression : Mandatory string containing the experssion to be evaluated, this must be URL encoded

precision  : Optional number defining the number of significant digits to be formatted



QUERY EXAMPLES
==============

Http Request examples:

https://localhost:port/swagger

https://localhost:port/api/math/?expression=2*(7-3)
  
https://localhost:port/api/math/?expression=2%2F3

https://localhost:port/api/math/?expression=2%2F3&precision=3

NOTE: Substitute "port" for correct number when running application


WEB APPLICATION
===============

The web application can be used for running calculations by entering expression and precision details in Non-URL encoded format. Once the details have been entered, users can then click the "Get Data" or "Post Data" buttons to view the evaluated result



DESIGN CONSIDERATIONS
=====================

Design considerations include:

1. Math API is held in separate project for deployment purposes

2. Web application and Swagger have been incorporated for testing

3. Angular JS has been incorporated to call Math API via GET and POST requests

4. Math API uses single "RunCalculation" to call open source APIs in line with technical discussions

5. Math API will attempt to use legacy product methods if any errors occur in line with user stories

6. Math API will report any errors through ILogger and by returning errors back to the user

7. Open source math links are stored in appsettings so they can be easily updated
