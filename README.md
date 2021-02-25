SUMMARY
=======

MVP Math is a RESTful API used for avaluating BEDMAS calculations via GET and POST requests

For example, API can be used to evaluate expressions such as "2*(7-3)"

The following criteria is met with the MVP Math API:

1. Expressions can perform the following:

   * Additions
   * Subtractions
   * Multiplications
   * Divisiotns

2. Multiple operations can be chained together

3. BEDMAS order of operation will be applied to expressions

4. Calculations shall be performed using the MVP Math algorithm.
   If execution fails API will attempt to use legacy algorithms.

NOTE: MVP Math replaces legacy "A Cool Calculation Company Saas Product"


EXECUTION
=========

Execution is limited to 10 seconds with a maximum of 10,000 request per day

Execution can tested through the web application detailed below of by using Swagger

For example, Swagger can be invoked when running the API by typing https://localhost:port/swagger



QUERY PARAMETERS
================

expression : Mandatory string containing the experssion to be evaluated, this must be URL encoded

precision  : Optional number defining the number of significant digits to be formatted



QUERY EXAMPLES
==============

Http Request examples:

https://server:port/api/math/?expression=2*(7-3)
  
https://server:port/api/math/?expression=2%2F3

https://server:port/api/math/?expression=2%2F3&precision=3



WEB APPLICATION
===============

The web application can be used for running calculations by entering expression and precision details in Non-URL encoded format.

Once the details have been entered, users can then click the "Get Data" or "Post Data" buttons to view the evaluated result



DESIGN CONSIDERATIONS
=====================

Design considerations include:

1. Math API is held in separate project for deployment purposes

2. Web application and Swagger have been incorporated for testing

3. Angular JS has been incorporated to call Math API via POST requests

4. Math API uses single "RunCalculation" to call open source APIs in line with technical discussions

5. Math API will attempt to use legacy product methods if any errors occur in line with user stories

6. Math API will report any errors through ILogger and by returning errors back to the user

7. Open source math links are stored in appsettings so they can be easily updated
