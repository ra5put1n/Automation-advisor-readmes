# How to use `json` method in Playwright?

`json` method is part of the `response` class in Playwright. It can be called like so:

```javascript
await response.json();
```

This takes the response from a request and returns it the JSON format.

It should be noted that if the reponse cannot be parsed by JSON.parse, this method will throw an error. Be sure to use this method only when the response is parsable from text to JSON.