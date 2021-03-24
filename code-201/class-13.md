# Local Storage

![local storage image](https://i.ytimg.com/vi/k8yJCeuP6I8/maxresdefault.jpg)

## Web Browser Local Storage

### What is HTML Web Storage?

HTML5 Storage is based on named `key/value` pairs. You store data based on a named key, then you can retrieve that data with the same key. The named key is a **string**. The data can be **any type** supported by JavaScript, including strings, Booleans, integers, or floats. However, the data is actually stored as a string. If you are storing and retrieving anything other than strings, you will need to use functions like `parseInt()` or `parseFloat()` to coerce your retrieved data into the expected JavaScript datatype.

With web storage, web applications can store data locally within the user's browser.

Before HTML5, application data had to be stored in **cookies**, included in every server request. Web storage is more secure, and large amounts of data can be stored locally, without affecting website performance.

Before local storage cookies are used to save some of data but it's going to slow your application, cookies size 4KB only but in local storage it can gives you at least 5MB.

### HTML Web Storage Objects

HTML web storage provides two objects for storing data on the client:

- **`window.localStorage`** - stores data with no expiration date
- **`window.sessionStorage`** - stores data for one session (data is lost when the browser tab is closed)

Before we can start using the local storage we need to check if the browser supports storage or not by using this code in your web applicatiion

```javascript
if (typeof(Storage) !== "undefined") {
  // Code for localStorage/sessionStorage.
} else {
  // Sorry! No Web Storage support..
}
```

### The localStorage Object

The localStorage object stores the data with no expiration date. The data will not be deleted when the browser is closed, and will be available the next day, week, or year.

```javascript
// Store
localStorage.setItem("lastname", "almasri");

// Retrieve
document.getElementById("result").innerHTML = localStorage.getItem("lastname");
```

The last example could be rewritten to use square bracket syntax instead:

```javascript
// Store
localStorage["lastname"] =  "almasri";

// Retrieve
document.getElementById("result").innerHTML = localStorage["lastname"];
```

**explaine**:

- Create a localStorage name/value pair with **name="lastname"** and **value="almasri"**
- Retrieve the value of "lastname" and insert it into the element with id="result"

To remove lastname from the Storage as below

```javascript
localStorage.removeItem("lastname");
```

### The sessionStorage Object

The `sessionStorage` object is equal to the `localStorage` object, except that it stores the data for only one session. The data is deleted when the user closes the specific browser tab.

The following example counts the number of times a user has clicked a button, in the current session:

```javascript
if (sessionStorage.clickcount) {
  sessionStorage.clickcount = Number(sessionStorage.clickcount) + 1;
} else {
  sessionStorage.clickcount = 1;
}
document.getElementById("result").innerHTML = "You have clicked the button " + sessionStorage.clickcount + " time(s) in this session.";
```

### STORAGE EVENT OBJECT

If you want to keep track programmatically of when the storage area changes, you can trap the storage event. The storage event is fired on the window object whenever `setItem()`, `removeItem()`, or `clear()` is called and actually changes something. For example, if you set an item to its existing value or call `clear()` when there are no named keys, the storage event will not fire, because nothing actually changed in the storage area.

You can listen to the storage event by this code:

```javascript
window.addEventListener("storage", handle_storage, false);
```

| PROPERTY | TYPE   | DESCRIPTION                                                           |
| -------- | ------ | --------------------------------------------------------------------- |
| key      | string | the named key that was added, removed, or modified                    |
| oldValue | any    | the previous value (now overwritten), or null if a new item was added |
| newValue | any    | the new value, or null if an item was removed                         |
| url      | string | the page which called a method that triggered this change             |

![storage image](https://camo.githubusercontent.com/2151e59ec943d17449dd33a421c07a115f0ed0cbcd5a13130048bb461c820522/68747470733a2f2f74656368676c696d7073652e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031332f30352f506173732d4c6f63616c53746f726167652d646174612d746f2d5048502d7573696e672d6a51756572792e6a706567)

### localStorage in JavaScript apps

![local storage image](https://i.morioh.com/de1cd54ffb.png)

To use localStorage in your web applications, there are five methods to choose from:

- **`setItem()`**: Add key and value to localStorage

    ```javascript
    window.localStorage.setItem('name', 'Wesam Almasri');
    ```

- **`getItem()`**: Retrieve a value by the key from localStorage

    ```javascript
    window.localStorage.getItem('user');

    // Return
    “{“name”:Waleed Afifi,”location”:”Lagos”}”
    ```

- **`removeItem()`**: Remove an item by key from localStorage

    ```javascript
    window.localStorage.removeItem('name');
    ```

- **`clear()`**: Clear all localStorage

    ```javascript
    window.localStorage.clear();
    ```

- **`key()`**: Passed a number to retrieve nth key of a localStorage

    ```javascript
    var KeyName = window.localStorage.key(index);
    ```

### localStorage limitations

As easy as it is to use localStorage, it is also easy to misuse it. The following are limitations, and also ways to NOT use localStorage:

1. Do not store sensitive user information in localStorage
2. It is not a substitute for a server based database as information is only stored on the browser
3. localStorage is limited to 5MB across all major browsers
4. localStorage is quite insecure as it has no form of data protection and can be accessed by any code on your web page
5. localStorage is synchronous, meaning each operation called would only execute one after the other
