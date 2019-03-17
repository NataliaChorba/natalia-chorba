# Playground API Test Automation

This is sample API automation project, which is built using  __[Postman](https://www.getpostman.com/)__


Follow Steps from below link to deploy application locally:

```
https://github.com/BestBuy/api-playground
```
## Tests could be run from Postman Runner or using Newman CLI

```
$ newman run best_buy_postman_tests.json -e local.postman_environment.json
```
Installation

The easiest way to install Newman is using NPM. If you have Node.js installed, it is most likely that you have NPM installed as well.

```
$ npm install -g newman
```

### Collection was imported from Swagger.

Checks before each test run of positive tests (set up on folder level):
* response code is 200
* response is valid JSON
* response body doesn’t contain text “error”
* response time is less than 300ms

Validations for each endpoint:
* Response scheme
* All required fields present in response
* All fields values are correct type
* Fields values are not empty (unless it’s allowed in spec)
* Negative checks for request parameters values: wrong type, empty, null, too small/large numbers

##Proposed list of testcases for Products and Categories endpoints (some of them are autometed):

Products:
* Get products: response body contains products
* “Total” element value > 0
* Default values of “limit” and “skip” parameters are correct
* Body.data length is equal to value of “limit” parameter
* When changing value of “skip” parameter, products are skipped
* Return only specific fields for products (e.g. name and price)
* Return products of specific category
* Return product with specific id
* Return product with invalid id
* Return product with valid but not existing id
* Sorting: asc and desc for price, name, type
* Filtering: for numeric fields return values greater than, less than and within a specific range
* Filtering: for string fields return values matching specific string and containing substring
* Filtering: check combination of different filters
* Filtering: apply sorting on filtered results
* Filtering: negative checks for filter values (incorrect range, invalid type, empty values)
* Filtering: return empty result
* Create a new product: positive case
* Create a new product with invalid fields values
* Create a new product with missing required fields
* Try to create a new product in read-only mode 
* Delete product by id
* Delete product: invalid id
* Delete product: not existing id
* Delete product: empty id
* Delete product which has already been deleted
* Update product: positive case
* Update not existing product
* Update product with invalid attributes values
* Update product with not existing id
* Update product with invalid id
* Update deleted product

Categories:
* Get categories
* Get categories: pagination
* Get categories: sorting
* Get categories: filtering by range of values
* Get categories: find specific categories by substring
* Get categories by id
* Get categories by id: invalid id
* Get categories by id: not existing id
* Create category: positive case
* Create category: id already exists
* Create category: invalid parameters
* Create category: missing parameters
* Create category: read-only mode
* Delete category by id
* Delete category: invalid id
* Delete categoryt: not existing id
* Delete category: empty id
* Delete category which has already been deleted
* Update category: positive case
* Update not existing category
* Update category with invalid attributes values
* Update category with not existing id
* Update category with invalid id
* Update deleted category

