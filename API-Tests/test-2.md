# API Test: Verifying creating a pet by dynamicly generated names

## Description
This API test script is designed to test the creation of a pet with a dynamically generated name.

## Request

- **URL**: `{{baseUrl}}/pet`
- **Method**: POST

### Variables
- `baseUrl`: The base URL of the API (`https://petstore.swagger.io/v2`).
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

## Pre-request Script and Tests

For detailed information on the pre-request script and tests, please refer to my [GitHub Gist](https://gist.github.com/leaviki90/4740220e5084ec0c64a44078d7ae041f).





