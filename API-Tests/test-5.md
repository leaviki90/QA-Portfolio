# API Test: Partial Update of a Post

## Request

- **URL**: `{{baseUrl}}/posts/{{id}}`
- **Method**: PATCH

## Authorization

- **Type**: Inherit from parent

## Variables

| Variable Name | Value                           |
|---------------|---------------------------------|
| `baseUrl`     | `https://jsonplaceholder.typicode.com`       |
| `id`          | `123`                           |  <!-- Set the ID of the post to be updated -->

## Body

```json
{
    "body": "Hello darkness my old friend"
}
```

## Tests

```javascript
// Verify that the status code is 200 (OK)
pm.test("Verify status code is 200", function () {
    pm.response.to.have.status(200);
});

// Verify that the response body contains the specified text
pm.test("Verify that responseBody contains 'Hello darkness my old friend'", function () {
    let responseBody = pm.response.text(); // Get the response body as text
    pm.expect(responseBody).to.include("Hello darkness my old friend"); // Check if the body contains the specified text
});
