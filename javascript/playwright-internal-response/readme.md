# What is the response class in Playwright?

Response class deals with the responses received by a page. It contains several methods to help in dealing with responses. The following are the methods and how you can use them:

## allHeaders

This method returns all the request HTTP headers in the response.

```javascript
await response.allHeaders();
```

## body

This returns the body of the response.

```javascript
await reponse.body();
```

### finished

This method waits for the response to finish and always returns `null`.

```javascript
await response.finished();
```

### headersArray

This returns an array with all the request HTTP headers in the response. Unlike `response.allHeaders()`, header names are NOT lower-cased. Headers with multiple entires exist in the array multiple times.

```javascript
await response.headersArray();
```

For more methods, [this](https://playwright.dev/docs/api/class-response#response-finished) document can be referred.

