# Welcome to Front End Development!
The power of JS in the browser is amazing. You can respond to user interactions, fetch content from servers/APIs (your own or other people's), build complex interfaces (even games!), and almost anything else you can imagine. Best of all, the client-side JS ecosystem is evolving at light speed. We're only going to scratch the surface today.

## What we talked about
1. Google Chrome devtools
    - **She is your best browser friend**, do not neglect her!
1. [navigator (the browser itself)](https://developer.mozilla.org/en-US/docs/Web/API/Navigator)
    - [A brief history of the user agent](https://webaim.org/blog/user-agent-string-history/)
    - [We can access the clipboard to copy/paste](https://developers.google.com/web/updates/2018/03/clipboardapi)
    - We can even make a phone vibrate using `navigator.vibrate()`!
1. [window (the browser window/tab)](https://developer.mozilla.org/en-US/docs/Web/API/Window)
    - Global variables
    - Browsing history (`window.history.back()` is the code equivalent of hitting the back button)
    - Pretty much anything you can do to the browser tab, you can do using the `window` object. Even `window.close()`!
1. [document](https://developer.mozilla.org/en-US/docs/Web/API/Document)
    - This is the [DOM (Document Object Model)](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
    > The Document Object Model (DOM) is the data representation of the objects that comprise the structure and content of a document on the web... the DOM represents an HTML or XML document in memory. (via MDN)
    - We can `query` for elements on the page by selector (preferrably `id` or `class`), 
    - We can use `addEventListener` to capture a user's interaction with the page
      - Common examples of events we listen for are `click`, `mouseover`, and `keydown`
      - For example, we can track every time the mouse moves over an element on our page by adding:

      ```js
      document.addEventListener('mouseover', event => console.log(event))
      ```
    - The `document` is made up of (among other things): `Nodes` and `Elements`.

      > Every object located within a document is a node of some kind. In an HTML document, each node is an element. (via MDN)
      
      >The element type is based on node. It refers to an element or a node of type element returned by a member of the DOM API... In an HTML document, elements are further enhanced by the HTML DOM API's HTMLElement interface... (via MDN)

    - We can access DOM elements/nodes using functions like:
        - `getElementsById()`
        - `getElementsByTagName()`
        - `getElementsByClassName()`

    - We can edit elements/nodes once they're rendered:

    ```js
    const title = document.getElementById('title')
    // <h2 id="title">Todo List</h2>

    title.innerText = 'I am the title!'
    // <h2 id="title">I am the title!</h2>
    
    title.setAttribute('id', 'big-title')
    // <h2 id="big-title">I am the title!</h2>

    ```

    - We can create new nodes like `elements` or `attributes` on-the-fly:

    ```js
    const button = document.createElement('button')

    // we have to append our new element to the DOM:
    document.body.append(button)

    button.innerText = 'Click me!' 
    button.setAttribute('id', 'action-button')
    ```

    - We can combine this with our earlier exploration of `eventListeners`:

    ```js
    button.addEventListener('click', () => {
      console.log('I have been clicked!')
    })
    ```
See the [GitHub repo here]() for the code examples we wrote in class!
