# API Test: Verify Status and Content of All Posts

## Request

- **URL**: `{{baseUrl}}/posts`
- **Method**: GET

## Authorization

- **Type**: Inherit from parent

## Variables

| Variable Name | Value                       |
|---------------|-----------------------------|
| `baseUrl`     | `https://jsonplaceholder.typicode.com`   |

## Body

- **Empty**: This GET request does not require a request body.

## Tests

```javascript
// Verify status code is 200
pm.test("Verify status code is 200", function () {
    pm.response.to.have.status(200);
});

// Verify all ids are integers
pm.test("Verify all ids are integers", function () {
    var jsonData = pm.response.json();
    jsonData.forEach(item => { 
        pm.expect(item.id).to.be.a("number"); // Is it a number?
        pm.expect(Number.isInteger(item.id)).to.be.true; // Is it an integer?
    });
});

// Verify Content-Type is present
pm.test("Verify Content-Type is present", function () {
    pm.response.to.have.header("Content-Type");
});

// Verify response time is less than 200ms
pm.test("Verify response time is less than 200ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(200);
});
