# wikipedia-search-engine

hello there, your task is to use debounce technique with the search input on the top of the page.

fork the repository and start working on it.

best of luck.

In this repository, I made changes to improve the search functionality. Specifically, I removed the `onkeyup` function from the `index.html` file and added an `addEventListener` function in the `script.js` file instead. Additionally, I created a debounce function for the search input field.

The debounce function is implemented as follows:

```
const debounce = (func, delay) => {
    let timeoutId;
    return (...args) => {
        if (timeoutId) {
            clearTimeout(timeoutId);
        }
        timeoutId = setTimeout(() => {
            func.apply(null, args);
        }, delay)
    };
};
```

Finally, I created a `debounceValidateInput` function that wraps the `validateInput` function in the debounce function with a delay of 600ms.

```
const debounceValidateInput = debounce(validateInput, 600);

document.querySelector('input[type="text"]').addEventListener('input', (event) => debounceValidateInput(event.target));
```

These changes make the search feature more responsive and efficient.
