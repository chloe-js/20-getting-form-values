# 20-getting-form-values
Getting Form Values
Runnable example 20-getting-form-values


Working with forms in JavaScript is a critical part of adding interactivity to websites. With JavaScript, you can not only get and set the values of different form fields, but also handle form submission and submit forms automatically. Forms don't necessarily need to be submitted to a server either: you can capture the onsubmit event and execute JavaScript in response to it, which means you can use forms to add, update, and remove DOM elements and manipulate the DOM in the same ways you can with button clicks, mouse movements and other events.

The first step to understanding how to work with forms in JavaScript is to learn how to get the values that a user has submitted. Take a simple login form for example:

<form method="POST" action="/login/">
  <div class="username">
    <label for="username">Username:</label>  
    <input type="text" id="username" name="username">
  </div>
  <div class="password">
    <label for="password">Password:</label>
    <input type="password" id="password" name="password">
  </div>
  <input type="submit" value="Login" />
</form>
In the above form, the username and password fields will be submitted to the /login/ URL on the server. On the server side, you would most likely access their values via the name attribute, which would be submitted as part of the POST request. With JavaScript you can access those values on the client side by getting the elements by their id and then accessing their value attribute. This allows you to manipulate, validate or do anything else you wish with the values before submitting them, or prevent submission altogether and do something else:

let user = document.getElementById('username');
let pass = document.getElementById('password');

// Now you can get their values
console.log(user.value);
console.log(pass.value);
Most form fields can be accessed in this way, but keep in mind that for some fields like checkboxes and multi-selection dropdowns, you may need to use more complex logic to access their values or whether or not they are "selected". You'll learn more about these other form operations as you write more complex code, and there are also JavaScript libraries that can serialize an entire form into a nice JavaScript object in a single line of code for these more complex situations! The basic example above is demonstrated in the runnable example below, where we've added an event listener to listen to the submit event on the form, and when it's triggered, execute a JavaScript function called handleSubmit(). The important thing to understand now is that a form element in your HTML is no different than any other element. It has attributes, properties and methods, all of which are accessible and mutable via JavaScript:
