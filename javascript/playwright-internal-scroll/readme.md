### How to perform scroll in Playwright?

To use the scroll feature in Playwright, you can use the .evaluate method on a Playwright page object, and pass in a JavaScript function to handle the scrolling.

Here is an example that scrolls down by 500 pixels:

```javascript
await page.evaluate(() => {
  window.scrollBy(0, 500);
});
```

You can modify the scroll amount and direction by changing the arguments to window.scrollBy. This returns a *Promise* that resolves when the scrolling action has completed.