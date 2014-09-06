---
title: MORE ADVANCED HTML LAYOUTS
files: []
editable: false
layout: 2-panels-tree

---
#'Forking' this module
If you check the url address bar of your browser, if it starts with `https://codio.com/anon/....` then this means it is an anonymous project and any changes you make will be lost when you close down the browser tab. This will be the case if you access the module from the Codio Courses screen.

To avoid losing changes, you can 'fork' the module into your own Codio account where it will appear in your projects list. To do this, select the **'Project->Fork'** menu item and choose a suitable name for the project.

#A few words about the Codio Guide
Before we start with this module here are a few pointers about using this Codio Guide.

If you've already read this in another Guide then skip to the next section.

![](.guides/img/guides-helper.jpg)

#The File Tree
The left most panel is the File Tree **(1)**. This is where your project's files are stored. You can open up files you see listed there by clicking on them.

#About the Codio Guide
The Codio Guide **(2)** is the content you are reading right now. It's worth knowing the following

- if you ever close the Guide tab by mistake, simply open in from the View menu **(3)**.
- you can expand and collapse the Guide's Table of Contents **(4)** with the Hamburger icon **(5)**
- you move from one section of the Guide to the next using either the Table of Contents or the Navigation Buttons (6)

#The Rocket Menu
The Rocket menu **(7)** is a dropdown menu that lets you load code into your file tree when you click it as different sections might want to show different bits of code.

You are usually encouraged to mess around with the live code. It is perfectly likely that you can wreck the code so pressing the Rocket menu button will restore the code again to its original state.

#Previewing
The Preview button **(8)** lets you run your web application. When you press it, it will open up a preview window so you can play with your app.

#Code Tabs
When you open some code from the file tree or the Codio Guide opens a file for you automatically, they will appear within a tab **(9)** in one of the panels. You can have several of these open at one time so you may need to click on the respective tab to get to see the file you want.


---
title: Overview
files: []
editable: false
layout: 2-panels-tree

---
This module builds on the materials we learnt in the 'My First Web Page' module.

We will learn how to flow logical blocks of content that can change as the browser resizes.

The image below shows what we will be building. 

![](.guides/img/result.png)

It is not especially pretty, but we want to concentrate on the basics and not spend too much time on details. In the next module, we will be building something much prettier.
---
title: Starting point
files:
  - path: index.html
    panel: 0
    ref: ""
    lineCount: 0
editable: true
layout: ""

---
You can select 'Starting Out' from the ![](.guides/img/rocket.png) Rocket menu to load the correct code for this section.

Take a look at the `index.html` file that has been opened. Preview it to see some very plain output.

There's not a lot to say here, so in the next section we'll add some basic CSS.
---
title: Experiment
files: []
editable: true
layout: ""

---
As with all Codio modules, we strongly encourage you to experiment as you go. You should hack the `index.html` and `main.css` files about without fear.

If you mess something up, you can restore the code by selecting the relevant item from the ![](.guides/img/rocket.png) Rocket menu.

![](.guides/img/rocketm.png)

---
title: Adding some colors
files: []
editable: true
layout: ""

---
Select 'Add Colors' from the ![](.guides/img/rocket.png) Rocket menu to load the correct code for this section.

We haven't changed the HTML other than to include the CSS file in the project, which you should have a look at and then preview.


---
title: Sizing our containers
files: []
editable: false
layout: ""

---
Select 'Sizing' from the ![](.guides/img/rocket.png) Rocket menu to load the correct code for this section.

If you preview, you can now see something more interesting starting to happen. Let's run through what we've done.

##Nicer HTML Tags
You'll notice that rather than using <div>s for all containers, we've actually taken advantage of some standard HTML tags that are provided for standard elements.

You don't *have* to use these, you can still use <divs>, but the advantage is that it makes your code more readable and you don't have to use classes. To all intents and purposes, though, they behave just like <div>s.

- <nav> is used for navigation menus
- <header> is used for a pages header section
- <footer> is pretty obvious

There are several other *semantic* elements offered by HTML, namely <section>, <article>, <aside>, <figure>, <figcaption>, <details>, <summary>, <mark>, <time>.

##Added some content
We've added some Latin text to the 'Content' container. This is done in the HTML.

We've also added in a few links to the 'Sidebar' container. Take a look at the HTML to see how links are set up.

##Sizing the menu
The menu now has a fixed size. This is done in the CSS (take a look at the <nav> selector) and in our case we've set the width to 400 pixels.

##Sizing the Content and Sidebar containers
We really want our Content and Sidebar containers to live side by side. Although they don't yet appear correctly (which we'll correct in the next section) we want:

- the Content to occupy 60% of the width
- the Sidebar to occupy 40% of the width

Next, we'll get them the appear side by side.
---
title: Floating the containers
files: []
editable: false
layout: ""

---
Select 'Floating' from the ![](.guides/img/rocket.png) Rocket menu to load the correct code for this section.

What happens next is actually quite tricky to understand. It is, without doubt, best understood by experimentation. So, once you've read the explanations, experiment like crazy with the CSS settings until you feel you understand it.

##A <div>'s natural flow
A <div> is a *block* level container. 

- It takes up the full width of its parent container
- It is a part of the natural flow of the document. This means it will be positioned underneath the previous block level element (<div>s in our case).

In the previous section we saw how the Content and Sidebar <div>s display underneath each other, even though we set the width properties to 60% and 40% wide (of their parent container's width) so they *ought* to fit side by side.

To get them to display correctly, we need to use a special CSS property called 'float'. If you look at `main.css` you can see that we have the following 

```
.content {
  background-color: #8bd6a9;
  width: 60%;
  float: left;  
}

.sidebar {
  background-color: #4baf73; 
  width: 35%; 
  float: right;
}
```

##What does 'float' do then?
The key thing that float does is to *remove the floated element from the normal block flow* and then *position the floated element usually to the left or right of the page*.

The problem with removing a block from the normal document flow is that subsequent *unfloated* blocks will appear in the normal document flow and will be display beneath the last unfloated block element.

##Looking at our page
Take a look at the preview of our page. Be sure to adjust the width of the preview window so you can see how the behavior changes as you resize.

- Menu and Header are unfloated blocks and so appear obediently beneath one another. 
- Content and Sidebar are floated and so imagine they are not even there  when you read the next bullet point
- The next unfloated block is the Footer. This will, and does, appear beneath the Header block. You can actually see its brown background sticking out below the Header block. We actually set the width of the Sidebar <div> to be 35% so we could see this happening. If we set it to 40%, it would be completely hidden from view.
- The reason that the text 'FOOTER' appears messily beneath the Sidebar is that the browser needs to show it and this is the earliest place on the page that it can fit.
---
title: Clearing this problem
files: []
editable: false
layout: ""

---
To make everything appear as it should be, we need to understand the CSS `clear` property.

The `clear` CSS property specifies whether an element can be next to floating elements that precede it or must be moved down (cleared) below them.

The clear property applies to both floating and non-floating elements.

When applied to non-floating blocks (in our case the Header <div>), it moves the border edge of the element down until it is below the margin edge of all relevant floats (in our case the Content and Sidebar <div>s).

So, you should go to `main.css` and change from this

```
footer {
  background-color: #b78366;   
  height: 80px;  
}
```

to this

```
footer {
  clear: both;
  background-color: #b78366;   
  height: 80px;  
}
```

Now run preview and all will be well with our page. If you like, you can restore the width of the Sidebar to 40%. 
---
title: Experiment
files: []
editable: false
layout: ""

---
Experiment a little, for example by

- removing or changing the float properties
- changing widths
- playing with the `clear` property

Really hack it about. You can always restore to its original state by selecting 'Floating' from the ![](.guides/img/rocket.png) Rocket menu.
---
title: Another float experiment
files: []
editable: false
layout: ""

---
Select 'Float Play' from the ![](.guides/img/rocket.png) Rocket menu.

You now have another project that should help you reinforce things using simple blocks.

When you preview, you'll see that Blocks 3 and 4 overlap one another. We covered the solution to this in the previous section (remember `clear: both`?).

Looking at the HTML, you can see that each block has its own ID and we've created selectors in the CSS for each of these. Go ahead and make changes with `float`, `width` and any other properties you want to modify.
---
title: Positioning blocks
files: []
editable: false
layout: ""

---
Select 'Float Position' from the ![](.guides/img/rocket.png) Rocket menu.

There is one more thing worth pointing out that allows us to do some powerful positional adjustments of blocks.

The `position` property allows us to adjust the way that a block displays.

##position:relative
Relative positioning allows you to adjust the positioning of a block *relative to itself*. In `main.css` we have 

```
#block2 {
  float: left; 
  position: relative;
  top: 20px;
  left: 10px;
}
```
This moves the position of the block from where the browser would normally render it and then moves it 20 pixels down from the top and also 10 pixels in from the left.

If we did not specify `top` or `left` then nothing would happen of course.

##position:absolute
Absolute positioning means that we want to position the block relative to the top left of the entire page. It also takes the block out of the normal flow. We also have an example of this in `main.css`

```
#block4 {
  position: absolute;
  top: 20px;
  left: 300px;
}
```

In the preview, you can see how this appears. Be sure to adjust the width of the preview window so you can see how the behavior changes as you resize.

##position:static
We don't use this, but it is the default behavior (as if we had not used `position` at all.)

##position:fixed
We don't use this in our example either, but it is a very cool feature. It will display at the position specified by top/bottom/right/left properties, no matter how you scroll or resize your browser. Try it out on block 4 for example and see what happens when you resize.

##Experiment
Yet again, we ask you to experiment with `position`, `top`, `left`, `bottom` and `right` until you have the the hang of it.
---
title: Another use for floating
files: []
editable: false
layout: ""

---
Select 'Float Images' from the ![](.guides/img/rocket.png) Rocket menu.

There is actually another very good usage for the `float` property. Let's say you have an image and you want your text to wrap nearly around the image. The `float` property can be used to accomplish this very easily.

If you preview, you'll see that the text displays inline with the image. 

Add the following to `main.css` and you'll see a much nicer result.

```
#first {
  float: left;
  width: 100px;
}

#second {
  float: right;
  width: 100px;
}
```
---
title: Fixed width layout
files: []
editable: false
layout: ""

---
Select 'Fixed Width' from the ![](.guides/img/rocket.png) Rocket menu.

What we are looking at here is a fixed width design that looks much like our earlier examples.

Preview and adjust the size of the preview window by moving the pane splitter. Notice how the layout is centered and retains a fixed width.

To see how we accomplished this, look at this piece of CSS 

```
.main {
  background-color: #dddddd;  
  width: 500px;
  margin: auto;
}
```

The `.main` container is a <div> that contains all the other <div>s on our page. 

- We have set the width to be 500 pixels. This means that all child containers are now restricted to this width.
- We also set `margin: auto;`. This tells the browser to apply margins on the left and right to be automatically set, which sets them equally based on the amount of available space between the main container and its parent, which is the <body> (the  entire browser page).

If you narrow down the preview pane, you will see that it does not do any resizing or reflowing of the content. This is because we defined a fixed width of 500 pixels.

So, if you want a web page to display equally well on a smartphone as it does on the desktop then using fixed width designs is a bad idea as it will not fit on smaller screen formats.
---
title: Introducing something cool
files: []
editable: false
layout: ""

---
We thought we'd introduce a really cool feature at this point that has nothing to fo with HTML layouts. 

If you look in the footer, you'll see that there are some icons. These are actually provided by a web based service called [Font Awesome](http://fortawesome.github.io/Font-Awesome/icons/).

See how much you can understand but don't worry too much if you are a bit overwhelmed.

##How it's done
We've created a list of items in the Footer section of our HTML 

```
<ul class='icons'>
  <li><i class="fa fa-camera-retro fa-2x"></i></li>
  <li><i class="fa fa-university fa-2x"></i></li>
  <li><i class="fa fa-graduation-cap fa-2x"></i></li>
  <li><i class="fa fa-share-alt-square fa-2x"></i></li>
</ul>
```

<ul> is the 'unordered list' HTML element and <li> are the individual elements that appear within the list. Without any CSS overrides, list items appear as bullet points, but we have styled them so they appear side by side.

Then, we've linked in an external library, which you can see in the <head> section of the HTML

```
  <link href="//maxcdn.bootstrapcdn.com/font-awesome/4.1.0/css/font-awesome.min.css" rel="stylesheet"> 
```

This is a web based service (it's actually nothing more than a remote CSS file) which we have simply plugged into our page.

By linking this in, we can use any icon available as a part of this service like this 

```
<i class="fa fa-camera-retro fa-2x"></i>
```

Notice the `class` reference to `fa-camera-retro`, which is the name of the icon we want to use (the camera one). 

`fa-2x` specifies the size (2x the basic size).

Finally, take a look at the way we have styled the list. 

```
.icons {
  list-style-type: none;
  padding: 4px;   
}

.icons li {
  display: inline-block;   
  margin: 20px 0 0 20px;
}
```

The first `.icons` selector relates to the <ul> element and the second one to the <li> element. 

`display: inline-block;` is actually an alternative to using `float`.

---
title: Spans
files: []
editable: false
layout: ""

---
Select 'Spans' from the ![](.guides/img/rocket.png) Rocket menu and preview it.

We'll conclude this module by looking at the <span> HTML element.

Whereas a <div> is a *block* level element, the <span> is an *inline* element. This means that it does not display on a new line, rather it is displayed inline with other elements, often just text.

Open up `index.html` and take a look at the last line of each verse.

```
  <p class="verse">
    <strong>Mary</strong> had a little lamb,<br/>
    His fleece was white as snow,<br/>
    And everywhere that Mary went,<br/>
    <span class='last-line'>The lamb</span> was sure to go.
  </p>
```

What we want to do is to style just an *inline* portion of the text so it has a different appearance to the rest.

If we just included a <span> without any styling override, we'd do the following and you would not be able to notice anything different about the way it renders.

```
<span>The lamb</span> was sure to go.
```

However by styling it, we can now apply a CSS rule that gives it the appearance you see when you preview it.

```
.last-line {
  margin-left: 10px;
  font: 30px 'Dancing Script', cursive;
}
```
---
title: Some extras
files: []
editable: false
layout: ""

---
We've actually done a couple of other interesting things on this page, just for the fun of it.

##Web Fonts
By default, browsers only know about a few basic fonts like Arial, Verdana, Times New Roman and a couple of others.

*Web Fonts* is a really cool thing that lets you use fonts that are hosted on the web. One great example is [Google Web Fonts](https://www.google.com/fonts) (click the link and explore).

To use a web font, we simply link to it in the <head> section of our HTML page

```
  <link href='http://fonts.googleapis.com/css?family=Dancing+Script:400,700' rel='stylesheet' type='text/css'>
```

Then, in the CSS, we can refer to it using

```
font: 30px 'Dancing Script', cursive;
```

##Bold, Italic & Emphasized Text
There are different ways to render text, all of which we have used in this example

- The <b> tag is one standard way and simply bolds the text
- The <strong> tag is another. This renders as bold but it is extremely useful for blind people as it also instructs their screen readers to change the way the text is actually spoken (it alters the tone). 
- The <i> tag italicizes your text
- You can also *emphasize* text using the <em> tag, which also renders it italic but the meaning is slightly different and implies it would be spoken differently. For example 'You really *should* learn to speak a foreign language'.
---
title: The End
files: []
editable: false
layout: ""

---
That's it! We've reached the end of this module and you are now well on the way to being a web developer.

Feel free to look up things on the web to strech your knowledge and above all - experiment.

Coding is not really an exact science. A bit like spoken languages, there are quirks and exceptions and bits of unexpected behavior that can only be understood by playing around and making mistakes.
