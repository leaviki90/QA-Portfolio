# API Test: Update a Post

## Request

- **URL**: `{{baseUrl}}/posts/{{id}}`
- **Method**: PUT

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
    "userId": "3",
    "id": "{{id}}",
    "title": "{{$randomCatchPhrase}}",
    "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
}
```

## Tests

```javascript
// Verify that the status code is 200 (OK)
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

// Verify that the response time is less than 200ms
pm.test("Response time is less than 200ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(200);
});

