Codeword combines the languages HTML, CSS, and Javascript. Outlined below are overviews of each:

Lesson 1 -> HTML 

The Webpage
-----
To create a **webpage**, we'll start by creating a file ending in `.html` in TextEdit on a Mac, or Notepad on Windows. For this lesson, we'll keep the naming simple and pretend we're creating an about webpage called `about.html`. 

Within `about.html`, we will include two **elements**:

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

![alt text](https://live.staticflickr.com/65535/49532761521_4999cde881_b.jpg "Basic Element")

You'll notice three things about this element:

- 1) It starts with `<p>` -> called an **opening tag**
- 2) It ends with `</p>` -> called a **closing tag**
- 3) It contains **content** -> `This is a paragraph of text. Here's a second sentence.`

**These three rules unite all HTML elements**, and they're easy to remember because of how similar they are to sentence structure:

- Sentences start with a capital -> Elements start with an **opening tag**
- Sentences end with a period -> Elements end with a **closing tag**
- Sentences contain other words -> Elements contain other HTML elements or text


Child Elements
-----
We can put elements inside of other elements. These are called **child elements**. Whereas a `<p>` element represents a paragraph, a `<b>` element represents bold text. We can emphasize our text by therefore combining these two elements:

```html
<p>This is a paragraph of text. Here's a <b>second</b> sentence.</p>
```

In the above case, the `<b>` element is the child of the `<p>` element:

![alt text](https://live.staticflickr.com/65535/49532761526_40059f10f2_b.jpg "Child Element")


Element Attributes
-----
Sometimes, we want to provide additional information about an element. This is where **attributes** come in. Attributes are placed in the **opening tag** of an element, and are used to further describe it:

An attribute added to our `<p>` element would look like this:

```html
<p title="First Paragraph">This is a paragraph. Here's a second sentence.</p>
```

Attributes come in pairs of words and have a few rules:

```html
title="First Paragraph"
```

- 1) The left word represents the attribute's **name** -> `title` in the above case
- 2) The right word represents the attribute's **definition** -> `"First Paragraph"`
- 3) Both words are separated by an **equals sign**: `=`

The `title` attribute shows a "tooltip" when you hover your mouse over its element:

![alt text](https://live.staticflickr.com/65535/49532983572_7714c7c33c_b.jpg "Title Tooltip")


Spaces and Line Breaks
-----
Computers don't care where you put your spaces:

**1) Multiple spaces are condensed into 1 space:**


```html
<p>I am a                           paragraph</p>
```

Looks the same as:


```html
<p>I am a paragraph</p>
```


![alt text](https://live.staticflickr.com/65535/49532983452_07e49d3a90_n.jpg "Condensed Spaces")

**2) Linebreaks are treated like spaces:**

```html
<p>I am a     
   paragraph</p>
```

Looks the same as:

```html
<p>I am a paragraph</p>
```

![alt text](https://live.staticflickr.com/65535/49532983452_07e49d3a90_n.jpg")

So just how do you add linebreaks? You can use the break element `<br>`, an **element with only an opening tag**:

```html
<p>I am a paragraph</p>

<p>I am a<br>
   paragraph</p>
```

![alt text](https://live.staticflickr.com/65535/49532983452_07e49d3a90_b.jpg "Adding Linebreaks")


Elements with only opening tags
-----
There's one rule we've learned so far that we are already going to break... that all elements have an opening **and** a closing tag. In fact, there are **a few elements that only have an opening tag**. The most common is the `<br>` element and the `<img>` element, which naturally, is used to display an image.

To define an `<img>` element, we simply provide it a `src` attribute, representing the *source* of the image file. For instance, if we uploaded our image to Flickr at `https://live.staticflickr.com/65535/49523044098_2ece3925df_b.jpg` - then our element would look like: 

```html
<img src="//live.staticflickr.com/65535/49523044098_2ece3925df_b.jpg">
```

Want to set a width or height? You can add them as attributes:

```html
<img src="//live.staticflickr.com/65535/49523044098_2ece3925df_b.jpg" width="300px" height="300px">
```


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
        <img src="//live.staticflickr.com/65535/49523044098_2ece3925df_b.jpg" width="300px" height="300px">
        <p title="Knock Knock...">
            Welcome to the Codeword about page! <br>
            The <b>easiest</b> place where you can learn to code
        </p>
    </body>
</html>
```

![alt text](https://live.staticflickr.com/65535/49532983572_7714c7c33c_b.jpg "Adding Linebreaks")

Lesson 2 -> CSS