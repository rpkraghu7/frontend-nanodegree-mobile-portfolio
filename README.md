# Website Performance Optimization portfolio project

### Guidelines to run the project

* The minified version of the production code is in **dist** folder.
* Run the **index.html** from the dist folder(minified version).
* Use **Ngrok.exe** to host the site on server to checkout pagespeedinsight score in the dist folder.
* Source code is in the **src** folder.
* To check the _source code_ open the **index.html** in the **src** folder.

(Note: To run the Ngrok.exe run it and open cmd and type `./ngrok http 800`)

### Optimizations made to _**index.html**_ :

* Removed the font css.
* Style css was inlined in the **index.html** file instead of loading in seperate file to reduce the size of page.
* **Media Queries** are used to prevent the render blocking of code due to css files.
* JavaScript files are made to run asynchronously using `async` attribute to prevent parser blocking.
* `img/profilepic.jpg` and `views/images/pizzeria.jpg` are compressed.
* `<script>` tag is moved down before the `<body>` tag.

## Optimizations made to `view/js/main.js` file: 

### To achieve 60fps:

* Moved `Math.sin((document.body.scrollTop / 1250))` outside the **for loop** to eliminate the Forced synchronous bottleneck.

### To resize pizzas within 5ms:

* Removed `Determinedx` function from the main.js.
* Altered the **Switch function** to change the width directly in `ChangePizzaSizes()` function to eliminate Forced Synchronous bottleneck.  