_Codeword_ makes it dead-simple to re-use custom HTML elements across a static site. **No javascript required.**

Basic Usage
===

Let's say you wanted to re-use a footer bar across a few different pages. With Codeword, your homepage (index.html) would look something like:

```html
<html>
    <head>
        <script src="https://codeword.it"></script>
    </head>

    <body>
        I am the content of a page.

        </footer-bar></footer-bar>
    </body>
</html>
```

To import this `footer-bar` codeword, just **add a folder called `codewords/`** to your website's root directory. Then add an HTML file of the same name:

```.
├── codewords
│   ├── footer-bar.html
├── index.html
```

Each codeword will now get automatically injected into your webpage based on its name and matching file.

To define a codeword's content, just **add a `definition` attribute** to its file, and use a `template` element to define the HTML that represents that codeword. Our `footer-bar.html` might look like this for instance:

```html
<footer-bar definition>

    <template>
        <footer>
            Copyright My Magic Company 2021
        </footer>
    </template>

</footer-bar>
```

The magic of Codeword, is that it not only automatically imports your codewords when developing locally, **Codeword also automatically removes itself when deploying your site** - avoiding all cross browser issues with web-components. So this is how your site is deployed:

```html
<html>
    <body>
        I am the content of a page.

        <footer>
            Copyright My Magic Company 2021
        </footer>
    </body>
</html>
```

Normal Usage
===

Codewords are great packages to move code around - but would be useless without also linking to some styles and scripts. So we can **inject `<style>` and `<script>` elements** for our CSS and Javascript. This is our styled footer bar, with a quick function:


```html
<footer-bar definition>

    <template>
        <footer onclick="say_hello()">
            Copyright My Magic Company 2021
        </footer>
    </template>

    <style>
        footer {
            text-align:center;
        }
    </style>

    <script>
        function say_hello () {
            alert('Oh hello!')
        }
    </scritp>

</footer-bar>
```

Our deployed site now looks like:

```html
<html>
    <head>
        <style>
            footer {
                text-align:center;
            }
        </style>

        <script>
            function say_hello () {
                alert('Oh hello!')
            }
        </script>
    </head>

    <body>
        I am the content of a page.

        <footer onclick="say_hello()">
            Copyright My Magic Company 2021
        </footer>
    </body>
</html>
```

Advanced Usage
===

This section reviews Codeword's support for variables, wildcard elements, and deployment instructions.

Variables
---

Codeword's can have variables. These are useful for creating more dynamic custom elements. First off:

**Codewords must have at least two names separated by a dash**: `<nav-bar>`, `<footer-bar>`, `<any-thing-you-can-think-of>` are all valid. 

**Variables must be 1 name long, and end in a dash**: `name-`, `year-`, `color-` are all proper.

To define a variable, simply shove it into the definition's template:

```html
<footer-bar definition>

    <template>
        <footer>
            Copyright My Magic Company <year->2021</year->
        </footer>
    </template>

</footer-bar>
```

The above `<year->` variable will have a default value of 2021, but can now be adjusted on the page that uses it as well:

```html
    <body>
        I am the content of a page.

        <footer-bar>
            <year->1950</year->
        </footer-bar>
    </body>
```

Or, if you find it cleaner, you can pass your variable's values in as attributes instead of elements (just don't forget that last dash):

```html
    <body>
        I am the content of a page.

        <footer-bar year-="1950">
        </footer-bar>
    </body>
```

Our compiled `index.html` will now look like:

```html
<html>
    <body>
        I am the content of a page.

        <footer>
            Copyright My Magic Company 1950
        </footer>
    </body>
</html>
```

Wildcards
---

Let's say you wanted to have a light and dark version of your `footer-bar` without defining 2 different codewords. Simply **use an `*` in your definition's name**, and then you can reference the wildcard with `footer1-`, `footer2-`, etc. Like so:

```html
<footer-* definition>

    <template>
        <footer data-color="<footer1-></footer1>">
            Copyright My Magic Company <year->2021</year->
        </footer>
    </template>

    <style>
        footer[data-color="light"] {
            background-color:white;
        }

        footer[data-color="dark"] {
            background-color:gray;
        }
    </style>

</footer-*>
```

Now in your `index.html`, just adjust the codeword's name:

```html
    <body>
        I am the content of a page.

        <footer-light>
        </footer-light>
    </body>
```

And now your compiled `index.html` will look like:

```html
<html>
    <style>
        footer[data-color="light"] {
            background-color:white;
        }

        footer[data-color="dark"] {
            background-color:gray;
        }
    </style>

    <body>
        I am the content of a page.

        <footer data-color="light">
            Copyright My Magic Company 1950
        </footer>
    </body>
</html>
```

Example - Longer Wildcards
---

The first part of the wildcard, `footer`, must match the first name of the codeword. But you can add as many matching names as you want. Building on the example, let's say we wanted a big and small version, on top of our light and dark versions. Here's the code:

```html
<footer-* definition>

    <template>
        <footer data-color="<footer1-></footer1>" data-size="<footer2-></footer2->">
            Copyright My Magic Company <year->2021</year->
        </footer>
    </template>

    <style>
        footer[data-color="light"] {
            background-color:white;
        }

        footer[data-color="dark"] {
            background-color:gray;
        }

        footer[data-color="small"] {
            font-size:12px;
        }

        footer[data-color="big"] {
            font-size:22px;
        }
    </style>

</footer-*>
```

Now in your `index.html`, just adjust the codeword's name:

```html
    <body>
        I am the content of a page.

        <footer-light-big>
        </footer-light-big>
    </body>
```

And now your compiled `index.html` will look like:

```html
<html>
    <style>
        footer[data-color="light"] {
            background-color:white;
        }

        footer[data-color="dark"] {
            background-color:gray;
        }

        footer[data-color="small"] {
            font-size:12px;
        }

        footer[data-color="big"] {
            font-size:22px;
        }
    </style>

    <body>
        I am the content of a page.

        <footer data-color="light" data-size="big">
            Copyright My Magic Company 1950
        </footer>
    </body>
</html>
```

Example - Varibles in CSS
---

Variables can also be used to link to styles like so:

```html
<footer-bar definition>

    <template>
        <footer data-style="<color->blue</color->">
            Copyright My Magic Company <year->2021</year->
        </footer>
    </template>

    <style>
        footer[data-style="blue"] {
            background-color:blue;
        }

        footer[data-style="black"] {
            background-color:black;
        }
    </style>

</footer-bar>
```

