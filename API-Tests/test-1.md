# API Test: Verify Status Code After Deleting a Pet

## Request

- **URL**: `{{baseUrl}}/pet/{{pet_ID}}`
- **Method**: DELETE

## Authorization

- **Type**: Inherit from parent

## Variables

| Variable Name | Value        |
|---------------|--------------|
| `baseUrl`     | `https://petstore.swagger.io/v2` |
| `pet_ID`      | `333`      |

## Body

- **Empty**: This DELETE request does not require a request body.

## Tests

```javascript
pm.test("Verify status code is 200 after deleting a pet", function () {
    pm.response.to.have.status(200);
});
