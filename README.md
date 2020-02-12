Lesson 1 -> HTML Basics


The Webpage
-----
To create a **webpage**, we'll start by creating a file ending in `.html` in TextEdit on a Mac, or Notepad on Windows. For this lesson, we'll keep the naming simple and pretend we're creating an about webpage called `about.html`. 

Within `about.html`, we will save a simple HTML webpage that includes two **elements**:

```html
<html>
	<body>About Page</body>
</html>
```

Just what the heck's an element? Keep reading.


The Element
-----
The first thing to know about HTML is that every webpage you've ever visited is made up of these things called **elements**. Just like any page of a book is made up of sentences, any webpage will be made up *exclusively* of elements. Elements describe the structure, text, and layout of a webpage.

Just like a normal sentence has certain rules to it (capitalize the first letter, end it with a period, and include a subject & verb), so will our elements. This is a *paragraph* element for instance:

```html
<p>This is a paragraph. Here's a second sentence.</p>
```

![alt text](https://www.flickr.com/photos/codeword/49523044098.jpeg "Basic Element")

You'll notice three things about this element:

- 1) It starts with an **opening tag**: `<p>`
- 2) It ends with a **closing tag**: `</p>`
- 3) It contains **content**: `This is a paragraph of text. Here's a second sentence.`

**These three rules unite all HTML elements**, and they're easy to remember because of how similar they are to sentence structure:

- Sentences start with a capital -> Elements start with an **opening tag**
- Sentences end with a period -> Elements end with a **closing tag**
- Sentences contain other words -> Elements contain other HTML elements or text


Child Elements
-----
We are allowed to put elements inside of other elements. These are called **child elements**. Whereas a `<p>` element is suitable to represent a paragraph, a `<b>` element represents bolded text. We can emphasize our text by therefore combining these two elements:

```html
<p>This is a paragraph of text. Here's a <b>second</b> sentence.</p>
```

In the above case, the `<b>` element is the child of the `<p>` element:

![alt text](https://www.flickr.com/photos/codeword/49523044098.jpeg "Child Element")


Element Attributes
-----
Sometimes, we want to provide additional information about an element without adjusting the content it contains. This is where **attributes** come in. Attributes are placed in the **opening tag** of an element, and are used to further decorate/describe it:

An attribute looks like this:

```html
<p title="First Paragraph">This is a paragraph. Here's a second sentence.</p>
```

Attributes come in pairs and also follow three rules: 

- 1) Both sides are separated by an **equals sign**: `=`
- 2) The left side represents the **attribute name**: `title` in the above case
- 3) The right side is surrounded in quotes and represents the **attribute value**: `"First Paragraph"`

The `title` attribute has the special behavior of showing a "tooltip" when you hover your mouse over its element, allowing the following behavior:

![alt text](https://www.flickr.com/photos/codeword/49523044098.jpeg "Title Tooltip")


Elements without closing tags
-----
There's one rule we've learned so far that we are already going to break... that all elements have a **closing tag**. There are in fact **a few elements that do not have a closing tag**. The most common is the `<img>` element, which naturally, is used to display an image.

To define an `<img>` element, we simply provide it a `src` attribute, representing the *source* of the file. For instance, if we uploaded our image to Flickr at `https://www.flickr.com/photos/codeword/49523044098.jpeg` - then our element would look like: 

```html
<img src="https://www.flickr.com/photos/codeword/49523044098.jpeg">
```

Want to set a width or height? You can add them as attributes:

```html
<img src="https://codeword.it/images/logo.jpeg" width="300px" height="500px">
```


Spaces and Line Breaks
-----
The spacebar key and enter key follow slightly special rules in our HTML file:

- **Multiple spaces are condensed to 1 space** -> these two paragraphs are displayed identically

```html
	<p>I am a paragraph</p>

	<p>I am a                           paragraph</p>
```

![alt text](https://www.flickr.com/photos/codeword/49523044098.jpeg "Condensed Spaces")

- **Linebreaks are treated as spaces** -> these two are also displayed in the same way


```html
	<p>I am a paragraph</p>

	<p>I am a     
       paragraph</p>
```

![alt text](https://www.flickr.com/photos/codeword/49523044098.jpeg "Linebreaks are Spaces")

- **How do you add linebreaks?** Use the break element `<br>` which like our `<img>` element, also contains **no closing tag**

```html
	<p>I am a paragraph</p>

	<p>I am a<br>
       paragraph</p>
```

![alt text](https://www.flickr.com/photos/codeword/49523044098.jpeg "Adding Linebreaks")

Note how the line breaks are also repected in the last example.


Putting it all together
-----
At this point, we're going to combine everything we've learned and create a basic about webpage. Our webpage should:

- Be viewable at `about.html` in our browser
- Reference our logo image
- Start with a brief paragraph and emphasize some text
- Separate our paragraph with a linebreak
- Include a "tooltip" that sets up a joke

And here is our beautiful about page:

```html
<html>
	<body>
		<img src="https://www.flickr.com/photos/codeword/49523044098.jpeg" width="300px" height="300px">
		<p title="Knock Knock...">
			Welcome to the Codeword about page! <br>
			The <b>easiest</b> place where you can learn to code
		</p>
	</body>
</html>
```

![alt text](https://www.flickr.com/photos/codeword/49523044098.jpeg "Adding Linebreaks")

Lesson 2 -> Defining Codewords