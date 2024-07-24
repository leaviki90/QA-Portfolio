# API Test: Pet Store

## Description
This API test script is designed to test the Pet Store API by performing the following actions:
1. Creating a new pet by generating random names for pets.
2. Logging in a user to get a token.
3. Verifying various response attributes.

## Request

- **URL**: `{{baseUrl}}/pet`
- **Method**: POST

### Variables
- `baseUrl`: The base URL of the API (`https://petstore.swagger.io/v2`).
- `username`: The username for logging in (`exampleUser`).
- `password`: The password for logging in (`examplePass`).
- `petName`: A randomly generated pet name.
- `randomID`: A randomly generated ID.

### Body
```json
{
  "name": "{{petName}}",
  "photoUrls": [
    "https://example.com/photo1",
    "https://example.com/photo2"
  ],
  "id": "{{randomID}}",
  "category": {
    "id": "{{randomID}}",
    "name": "{{petName}}"
  },
  "tags": [
    {
      "id": "{{randomID}}",
      "name": "{{petName}}"
    },
    {
      "id": "{{randomID}}",
      "name": "{{petName}}"
    }
  ],
  "status": "available"
}

## Tests

```javascript

pm.test("Verify status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Verify response is JSON", function () {
    pm.response.to.be.json;
});

pm.test("Verify that response time is less than 200ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(200);
});

const response = pm.response.json();

pm.test("Verify that response contains id", function () {
    pm.expect(response).to.have.property('id');
});

pm.test("Verify pet status is available", function () {
    pm.expect(response.status).to.eql("available");
});

pm.test("Verify that Pet name is correct", function () {
    pm.expect(response.name).to.eql(pm.collectionVariables.get("petName"));
});

pm.test("Verify that response contains photoUrls", function () {
    pm.expect(response.photoUrls).to.be.an('array').that.is.not.empty;
});

pm.test("Verify that response contains category", function () {
    pm.expect(response).to.have.property('category');
    pm.expect(response.category.name).to.eql(pm.collectionVariables.get("petName"));
});

pm.test("Verify that response contains tags", function () {
    pm.expect(response.tags).to.be.an('array').that.is.not.empty;
    response.tags.forEach(tag => {
        pm.expect(tag.name).to.eql(pm.collectionVariables.get("petName"));
    });
});


