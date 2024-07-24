# API Test: Verify Deletion of a Post

## Request

- **URL**: `{{baseUrl}}/posts/{{id}}`
- **Method**: DELETE

## Authorization

- **Type**: Inherit from parent

## Variables

| Variable Name | Value                       |
|---------------|-----------------------------|
| `baseUrl`     | `https://jsonplaceholder.typicode.com`   |
| `id`          | `33`                       |

## Body

- **Empty**: This DELETE request does not require a request body.

## Tests

```javascript
// Test to verify that the response is an empty object
pm.test("Response is an empty object", function () {
    let responseBody = pm.response.json(); 
    pm.expect(responseBody).to.be.an('object').that.is.empty; // Check if the body is an empty object
});

// Test to verify that the status code is 200
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
