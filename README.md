<!--
Market: SF
-->

![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)

<!--Hook: So who has ever signed up for something online?  What do you usually need to do?  What about buying something online?

Usually there is an interaction with a form of some sort.  So you put in a username, password, maybe an email or credit card information.  Then that information is sent to a server somewhere.  Who's ever had a frustrating experience with one of these forms?

Well, as we go through this course we will learn some ways to reduce that frustration. -->

<!--11:05 5 minutes -->

# HTML Forms

## Why is this important?
<!-- framing the "why" in big-picture/real world examples -->
*This workshop is important because:*

Forms are an important way a web application receive user input. The proper use of forms makes it easier to develop accessible websites with a good user experience.

## What are the objectives?
<!-- specific/measurable goal for students to achieve -->
*After this workshop, developers will be able to:*

- **Evaluate** the proper usage of HTML form and input options
- **Compare and contrast** a `method` and an `action`
- **Create** forms that generate query parameters

## Where should we be now?
<!-- call out the skills that are prerequisites -->
*Before this workshop, developers should already be able to:*

- **Write** HTML & JavaScript
- **Understand** the basics of the client/server model
- **Understand** the basics of jQuery

<!--11:10 10 minutes-->

### An Example `<form>` Element (Tag)

```html
<form method="POST" action="/page">
  <input type="text" name="pageName" />
  <input type="submit" value="Create" />
</form>
```

#### Attributes

In the opening of the `<form>` tag you can see two attributes: `method` & `action`

- **method**: the HTTP verb (method) that the browser uses to submit the form.
- **action**: the path of the HTTP request page that processes the information submitted via the form.

>A `route` is simply a combination of a method & action. For example `GET '/page'` or `POST '/users'` are both valid routes.

>For now simply understand that it is convention for [GET](http://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html#sec9.3) to be used in a request when the client wants to receive data, and for [POST](http://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html#sec9.5) to be used in a request when the client wants to send data.

<!-- Keep code above visible -->

### Challenge: Doomed?

Create an html `form` that, on submit, sends the user to "hasthelargehadroncolliderdestroyedtheworldyet.com". Hint: what's the form action? Bonus: Can you change the submit button to say "Are we doomed?".

<details>
<summary>Example solution</summary>

```html
<form action="http://hasthelargehadroncolliderdestroyedtheworldyet.com" method="GET">
  <input type="submit" value="Are we doomed!?">
</form>
```

</details>


**Client / Server Model**

![client/server](https://mdn.mozillademos.org/files/4291/client-server.png)

<!--11:20 20 minutes -->

## Common Inputs

<!--Ask dev to just read first column -->

| Field Type | HTML Code | Widget (Control) | Notes |
|:-- |:-- |:-- |:-- |
| plain text | `<input type="text">` | [`<input type="text">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/text) | the type attribute can be omitted |
| password field | `<input type="password">` | [`<input type="password">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/password) | echoes dots instead of characters |
| text area | `<textarea></textarea>` | [`<textarea></textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) | a more customizable plain text area |
| checkbox | `<input type="checkbox">` | [`<input type="checkbox">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox) | can be toggled on or off |
| radio button | `<input type="radio">` | [`<input type="radio" name="group"> <input type="radio" name="group">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/radio) | can be grouped with other inputs |
| drop-down lists | `<select><option>` | [`<select><option>Option 1</option><option>Option 2</option></select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) | [check here for more info](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) |
| file picker | `<input type="file">` | [`<input type="file">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/file) | pops up an “open file” dialog |
| hidden field | [`<input type="hidden">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/hidden) |  | nothing there!
| submit button | `<input type="submit">` | [`<input type="submit">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/submit) | activates the form's submission <br/>(a `POST` request or <br/>Javascript action) |

<!-- Images -->
[text]:   https://raw.github.com/h4w5/html_form_cheatsheet_images/master/input-text.png
[area]:   https://raw.github.com/h4w5/html_form_cheatsheet_images/master/textarea.png
[check]:  https://raw.github.com/h4w5/html_form_cheatsheet_images/master/input-checkbox.png
[radio]:  https://raw.github.com/h4w5/html_form_cheatsheet_images/master/input-radio.png
[select]: https://raw.github.com/h4w5/html_form_cheatsheet_images/master/select-option.png
[file]:   https://raw.github.com/h4w5/html_form_cheatsheet_images/master/input-file.png
[submit]: https://raw.github.com/h4w5/html_form_cheatsheet_images/master/input-submit.png

<!--CFU: Whip-around, see if we can remember all the input types (no peeking) -->

### Important Attributes

All input types (including `<textarea>`s):

<!--Whip-around-->

- **`name`**: the key used to describe this data in the HTTP request.
- **`id`**: the unique identifier that other HTML elements, JavaScript and CSS use to access this
  element in the browser.
- **`placeholder`**: not a default value, but a useful HTML5 addition of a data "prompt" for an input.
- **`autofocus`**: defaults the cursor to a specific input when the page originally loads. You can only have one autofocus on your page.
- **`disabled`**: a Boolean attribute indicating that the "widget" is not available for interaction.
- **`required`**: a Boolean attribute indicating that the field must have a value / cannot be left empty.

All input types (excluding `<textarea>`s):

- **`value`**: the default data that is assigned to the element.
- **`type`**: the type of data that is being input (affects the "widget" that is used to display this
  element by the browser).

Radio buttons or checkboxes:

<!--Whip-around -->

- **`checked`**: a Boolean that indicates whether the control is selected by default (is false unless).
- **`name`**: the group to which this element is connected. For radio buttons, only one element per
  group (or name) can be checked.
- **`value`**: the data or value that is returned for a specific group (a multi-element control), if
  this element is checked.
  
### Challenge: Login Form

Create an html `form` with two inputs: one for a username (named "username"), the other for password (named "password") (normally you don't see your password when you type it, so make sure it's blocked out!). What happens in the URL when you click submit?

<!-- Example solution

```html
<form>
	<input type="text" name="username" placeholder=" username..." required>
	<input type="password" password="password" placeholder="password..." required>
	<input type="submit">
</form>
```

-->

<!--11:40 10 minutes-->

## Form Submission Experiments

**1)** Given the following HTML...

``` html
<form>
    <input name="instrument" value="bongos"> <!-- Text Field -->
    <input type="submit">                   <!-- Submit Button -->
</form>
```

<!--Have students answer first before showing answer -->

<details><summary>What endpoint/action are we submitting to? (Click Here)</summary>
We did not supply a form `action`. That means that it will default to the current endpoint. In other words, you will refresh the current page.
</details>

<details><summary>What data will be submitted to the server? (Click Here)</summary>
instrument: "bongos"
</details>

<details><summary>What will that data look like? How will it be formatted? (Click Here</summary>
?instrument=bongos
</details>


**2)** Given the following HTML...

``` html
<form action="https://musicbrainz.org/search" method="GET">
    <label for="artist">Search by Music Artist</label>
    <input id="artist" name="query" value="Adele">
    <input name="type" value="artist" hidden>
    <input type="submit">
</form>
```

<details>
<summary>**What endpoint/action are we submitting to?** (Click Here)</summary>
<br>
We are making a "GET" request to "https://musicbrainz.org/search".
</details>

<details>
<summary>**What data will be submitted to the server?** (Click Here)</summary>
<br>
query: "Adele", type: "artist"
</details>

<details>
<summary>**What will that data look like? How will it be formatted?** (Click Here)</summary>
<br>
It will be in the form of a query parameter: `?query=adele&type=artist`
</details>

<!--11:50 10 minutes -->

<!--Drop this code in a script tag into HTML -->

## Form Submission & jQuery
> **Important**: You do not need jQuery to submit a form. You do not need jQuery to submit a form. You do not need jQuery to submit a form.

Sometimes we want to submit a form, in the background, without ever refreshing the page. This is a common pattern in modern "single page applications". How do you submit form data *in the background*?

When a form is submitted it triggers the `submit` event. We can listen to this event using jQuery.

``` javascript
$("form").on("submit", function(event){
    alert("See you later! You're submitting a form!")
})
```

In order to **stop** the form from submitting, we have to prevent its *default* behavior.

``` javascript
$("form").on("submit", function(event){
    event.preventDefault(); // Stops the form from submitting!
    alert("You're not going anywhere! (You prevented the form from submitting).")
})
```

If we want to grab a value from our form, we can use jQuery's [`val` method](http://api.jquery.com/val/).

``` javascript
$("input#artist").val(); // "Adele"
$("input[name=query]").val(); // "Adele"
$("input#artist").attr("name"); // "query"
```

> **Note**: jQuery's `text` method will not work on inputs!

If we want to grab **all** of the data (name/value pairs) in the form, we can use jQuery's [`serialize` method](http://api.jquery.com/serialize/).

``` javascript
$("form").serialize(); // e.g. "?query=Adele&type=artist"
```

Generally we will do this when the form is `submit`ted. Calling `preventDefault` allows us to instead submit the form data in the background without ever refreshing the page!

``` javascript
$("form").on("submit", function(event){
    event.preventDefault(); // Stops the form from submitting!
    var formData = $(this).serialize();
    console.log("form data is:", formData);
    // ... verify the user didn't miss anything
    // ... send the form data to the server
    // ... wait for a response
    // ... (we'll learn these additional steps soon enough)
```

> **Reminder**: You do not need jQuery to submit a form.

<!--12:00 5 minutes -->

## Sexy Forms

#### The `<label>` Element
We encourage you to always use the optional `<label>` tag with each of your form inputs.

>"This is the most important element if you want to build accessible forms." — MDN

There are two ways to use labels correctly:

```html
<!-- Simple (nested) label example -->
<label>Username
  <input type="text" name="username" />
</label>

<!-- Using the "for" attribute with the input's id -->
<!-- This is the preferred method if you are using Bootstrap -->
<label for="password">Username</label>
<input id="password" type="text" name="password" />
```

> Make sure the label's `for` attribute matches the input's `id` attribute!

<!--12:05 10 minutes -->

## Common Validations

Form validations help to prevent users from submitting bad data to the server. They are very important to improve UX, but *do not increase the security* of the application. They can detect:

* a missing or empty field (required)
* an email address that was missing an "@" symbol (wrong pattern)
* a password that is obiously too short (invalid length)

#### `required` attribute

Try submitting the below form without entering your name:

```html
<form>
  <label for="colorField">What is your favorite color?</label>
  <input id="colorField" name="favColor" required>
  <button>Submit</button>
</form>
```
Notice the `required` attribute on the input. Therefore, the form will not submit until some information is entered into the field.

#### `pattern` attribute

```html
<form>
  <label for="kindOfBob">Do you go by bob or bobert?</label>
  <input id="kindOfBob" name="bobType" pattern="bob|bobert" required>
  <button>Submit</button>
</form>
```

The `pattern` attribute allows us to specify the values we will accept. In this case only `bob` or `bobert` are acceptable. There are [lots of useful variations](https://www.w3schools.com/tags/att_input_pattern.asp).

#### `length` attribute

You may need the user to enter a specific amount of characters. Let's say you need a username to be at least 6 characters. You can use the `minlength` or `maxlength` attributes to help.

```html
<form>
  <label for="password">What's your password?</label>
  <input id="password" type="password" name="password" minlength="8" required>
  <button>Submit</button>
</form>
```

<!--12:15 10 minutes -->

## Independent Practice

**1)** Create an html form that contains the html5 [color-picker](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/color) input (named "i"). When the user picks a color, let's say one with the hex code `#18967A`, and clicks submit, redirect them to, e.g. "https://www.wolframalpha.com/input/?i=%2318967A".

> The `#` character automatically gets converted to `%23` in this context because it is a special character.

<details>
<summary>Example solution</summary>

```html
<form action="https://www.wolframalpha.com/input/" method="GET">
  <input type="color" name="i">
  <input type="submit" value="search">
</form>
```

</details>

**2)** Create an html form that searches github for code examples that match a specific query (q) and language (l). Use `html`, `javascript`, and `css` as the languages the user can select from a drop down menu. A search for "audio" in the language "javascript" should direct to https://github.com/search?q=audio&l=javascript.

<details>
<summary>Example solution</summary>

```html
<form action="https://github.com/search" method="GET">
  <input type="text" name="q" placeholder="search">
  <select name="l">
    <option value="HTML">HTML</option>
    <option value="Javascript">Javascript</option>
    <option value="CSS">CSS</option>
  </select>
  <input type="submit" value="Search Github">
</form>
```

</details>

<!-- 12:25 5 minutes -->

## Closing Thoughts

* What is a form `method` and a form `action`?
* How do we prevent a form's submission from leaving or refreshing the current page?
* Do validations make our application more secure?
* What does jQuery's `.serialize` method do?

## Additional Resources

MDN has a number of exhaustive resources on HTML forms and inputs. It can be a lot to absorb, so look for patterns and try to grasp the big picture.

* [HTML Form Reference](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms)
* [HTML Input Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
* [Native Form Widgets](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms/The_native_form_widgets)
* [Form Validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms/Data_form_validation)
* [Inspiration for Text Inputs](http://tympanus.net/codrops/2015/01/08/inspiration-text-input-effects/)

## Licensing
All content is licensed under a CC­BY­NC­SA 4.0 license.
All software code is licensed under GNU GPLv3. For commercial use or alternative licensing, please contact legal@ga.co.
