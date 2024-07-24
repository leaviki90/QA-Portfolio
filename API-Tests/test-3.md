# API Test: Create a Post with Random Data

## Request

- **URL**: `{{baseUrl}}/posts/`
- **Method**: POST

## Authorization

- **Type**: Inherit from parent

## Variables

| Variable Name | Value                           |
|---------------|---------------------------------|
| `randomNumber`| Random number between 1 and 100 |

## Body
```json
{
    "userId": {{randomNumber}},
    "id": "",
    "title": "{{$randomCatchPhraseNoun}}",
    "body": "{{randomText}}"
}
```
## Pre-request scripts
```javascript
pm.collectionVariables.set("randomNumber", _.random(1, 100));

let words = ["Lorem", "ipsum", "dolor", "sit", "amet", "consectetur", "adipiscing", "elit", 
             "sed", "do", "eiusmod", "tempor", "incididunt", "ut", "labore", "et", "dolore", 
             "magna", "aliqua", "Ut", "enim", "ad", "minim", "veniam", "quis", "nostrud", 
             "exercitation", "ullamco", "laboris", "nisi", "ut", "aliquip", "ex", "ea", "commodo", 
             "consequat", "Duis", "aute", "irure", "dolor", "in", "reprehenderit", "in", "voluptate", 
             "velit", "esse", "cillum", "dolore", "eu", "fugiat", "nulla", "pariatur"];
function generateRandomText(wordCount) {
    let randomText = [];
    for (let i = 0; i < wordCount; i++) {
        let randomIndex = Math.floor(Math.random() * words.length);
        randomText.push(words[randomIndex]);
    }
    return randomText.join(" ");
}

let randomText = generateRandomText(50);
pm.globals.set("randomText", randomText);
```
## Tests

```javascript
// Verify that the status code is 201 (Created)
pm.test("Verify status code is 201", function () {
    pm.response.to.have.status(201);
});

// Verify that the length of random text is up to 50 words
pm.test("Verify random text length is up to 50 words", function () {
    let randomText = pm.globals.get("randomText");

    // Verify that the text has up to 50 words
    pm.expect(randomText.split(" ").length).to.be.below(51);
});

