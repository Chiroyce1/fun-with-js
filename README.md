# weird-js
#### Demonstrating some weird features of JavaScript

### [Magically Closing a Tab](https://chiroyce1.github.io/weird-js/close-tab/)
This demonstrates how a tab opened by a regular HTML link can be closed automatically. The link will be clicked, and then the click can be prevented by using a simple function called `preventDefault()`
```js
linkElement.addEventListener("click", (e) => {
    e.preventDefault(); // Prevent the link from being clicked
})
```
and then, opening a new tab (using `window.open`) and closing it after a while. Users might think this is a link that takes them to the new page but it actually is a new `window` object made by JavaScript, when we got input from the user, we cancelled it and used it for another purpose. 

```js
linkElement.addEventListener("click", (e) => {
    e.preventDefault(); // Prevent the user from clicking the link
    tab = window.open('https://wikipedia.org') // Open a new tab
    setTimeout(() => {
        tab.close(); // Close the newly opened tab after 2 seconds
    }, 2000);
})
```
Kinda scary but fun at the same time.

---

### [Faking copying some text](https://chiroyce1.github.io/weird-js/fake-copy/)
This demonstrates how whatever you copy from a website can be modified, when you copy text, `preventDefault()` is called to prevent copying it, and `clipboardData.setData()` is used to modify the contents of the clipboard. 

```js
element.addEventListener("copy", (e) => {
  e.clipboardData.setData('text/plain', "Foo Bar"); // Use the event to copy something into the users clipboard
  e.preventDefault(); // Cancel the actual event.
})
```
This is why you should always be careful when you copy text from a website and paste it somewhere else. 

---

<script>console.log("JavaScript works when using GitHub pages along with markdown!")</script>
