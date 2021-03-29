# What is the Web Storage API?
The Web Storage API is a set of mechanisms that enable browsers to store key/value pairs. It is designed to be much more intuitive than using cookies.


The key/value pairs represent storage objects, which are similar to objects except they remain intact during page loads, and are always strings. You can access these values like an object or using the getItem() method (more on that later).


# What is localStorage in JavaScript?
localStorage is a property that allows JavaScript sites and apps to save key/value pairs in a web browser with no expiration date. This means the data stored in the browser will persist even after the browser window is closed.


# What is the difference between sessionStorage and localStorage?
The Web Storage API consists of two mechanisms: sessionStorage and localStorage. Both sessionStorage and localStorage maintain a separate storage area for each available origin for the duration of the page session.

The main difference between sessionStorage and localStorage is that sessionStorage only maintains a storage area while the browser is open (including when the page reloads or restores) while localStorage continues to store data after the browser is closed. In other words, whereas data stored in sessionStorage is cleared when the page is closed, data stored in localStorage does not expire.


# Where is localStorage stored?
In Google Chrome, web storage data is saved in an SQLite file in a subfolder in the user’s profile. The subfolder is located at \AppData\Local\Google\Chrome\User Data\Default\Local Storage on Windows machines and ~/Library/Application Support/Google/Chrome/Default/Local Storage on macOS

Firefox saves storage objects in an SQLite file called webappsstore.sqlite, which is also located in the user’s profile folder.


# What is Window.localStorage?
The localStorage mechanism is available via the Window.localStorage property. Window.localStorage is part of the Window interface in JavaScript, which represents a window containing a DOM document.

The Window interface features a wide range of functions, constructors, objects, and namespaces. Window.localStorage is a read-only property that returns a reference to the local storage object used to store data that is only accessible to the origin that created it.

# How does localStorage work?
To use localStorage in your web applications, there are five methods to choose from:

1. setItem(): Add key and value to localStorage
2. getItem(): This is how you get items from localStorage
3. removeItem(): Remove an item by key from localStorage
4. clear(): Clear all localStorage
5. key(): Passed a number to retrieve the key of a localStorage



* setItem(): How to store values in localStorage
Just as the name implies, this method allows you to store values in the localStorage object.

It takes two parameters: a key and a value. The key can be referenced later to fetch the value attached to it.

window.localStorage.setItem('name', 'Obaseki Nosa');
Where name is the key and Obaseki Nosa is the value. Also note that localStorage can only store strings.

To store arrays or objects, you would have to convert them to strings.

To do this, we use the JSON.stringify() method before passing to setItem().

        const person = {
            name: "Obaseki Nosa",
            location: "Lagos",
        }

        window.localStorage.setItem('user', JSON.stringify(person));



* getItem(): How to get items from localStorage
To get items from localStorage, use the getItem() method. getItem() allows you to access the data stored in the browser’s localStorage object.

getItem() accepts only one parameter, which is the key, and returns the value as a string.

To retrieve a user key:

        window.localStorage.getItem('user');
This returns a string with value as:

“{“name”:”Obaseki Nosa”,”location”:”Lagos”}”
To use this value, you would have to convert it back to an object.

To do this, we make use of the JSON.parse() method, which converts a JSON string into a JavaScript object.

        JSON.parse(window.localStorage.getItem('user'));



* removeItem(): How to delete localStorage sessions
To delete local storage sessions, use the removeItem() method.

When passed a key name, the removeItem() method removes that key from the storage if it exists. If there is no item associated with the given key, this method will do nothing.

        window.localStorage.removeItem('name');
        


* clear(): How to delete all items in localStorage
Use the clear() method to delete all items in localStorage.

This method, when invoked, clears the entire storage of all records for that domain. It does not receive any parameters.

        window.localStorage.clear();