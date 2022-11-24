---
layout: default
title: JavaScript Basics
---

<h1>JavaScript Basics</h1>

<h2>1. A Simple Alert Box</h2>
<p>This example shows a simple alert box when a button is clicked</p>

<button onclick="test1()">Try it</button>
<script>
function test1() {
  alert("Hello! I am an alert box!");
}
</script>

<p>The script:</p>

```
<button onclick="test1()">Try it</button>
<script>
function test1() {
  alert("Hello! I am an alert box!");
}
</script>
```

<h3>Explanation</h3>

<p> 
In the code above, you can see the JavaScript inside the &lt;script&gt; tags. 
This uses the JavaScript ‘Function’ object and a dialog box object.
The function is executed by the ‘onclick=’ event handler, assigned to an HTML button.
</p>

<p><a href="https://www.w3schools.com/jsref/met_win_alert.asp">Reference for this script</a></p>
<hr>

<h2>2. Write something into a document</h2>
<p>This example shows how JS can manipulate text on a document</p>
<button onclick="test2()">Click this button and watch the text below change.</button>
<p style="font-weight:bold;" id="demo1">Watch this text change.</p>
<script>
function test2() {
  document.getElementById("demo1").innerHTML = "Hello World! How are you today?";
}
</script>

<p>The script:</p>

```
<button onclick="test2()">Click this button and watch the text below change.</button>
<p style="font-weight:bold;" id="demo1">Watch this text change.</p>
<script>
function test2() {
  document.getElementById("demo1").innerHTML = "Hello World! How are you today?";
}
</script>
```

<h3>Explanation</h3>

<p> 
This code illustrates a highly useful JavaScript method for accessing the Document Object.<br>
JavaScript uses ‘dot syntax’ to access this: <br>
<span style="font-family:font-family: Courier, monospace;">document.getElementById().innerHTML = </span><br>
This is a JavaScript method for parsing the document in search of an HTML tag with the id “demo1”.<br>
Once the tag with ID “demo1” is located, whatever is placed after the = sign is displayed inside the &lt;p&gt; tag of the document.
</p>

<p><a href="https://www.w3schools.com/jsref/met_document_getelementbyid.asp">Reference for this script</a></p>
<hr>

<h2>3. Extend the above to get user input and output it to the document</h2>
<p>This example shows how JS can take user input and join it to another text and output it.</p>
<p>When you enter a name and submit, a message will be displayed underneath.</p>

<p>Enter your name, or any name: <input type="text" id="inputName"><button onclick="test3()">Submit</button></p>
<p>The message will appear here: <span id="output1"></span></p>

<script>
function test3() {
  var yourName = document.getElementById("inputName").value;
  document.getElementById("output1").innerHTML = "Hello " + yourName + ". How are you today?";
}
</script>

<p>The script:</p>

```
<p>Enter your name, or any name: <input type="text" id="inputName"><button onclick="test3()">Submit</button></p>
<p>The message will appear here: <span id="output1"></span></p>

<script>
function test3() {
  var yourName = document.getElementById("inputName").value;
  document.getElementById("output1").innerHTML = "Hello " + yourName + ". How are you today?";
}
</script>
```


<h3>Explanation</h3>
<p> 
An HTML input box with an ID of “inputName” accepts user input. The Button calls the JavaScript function.<br>
The function gets the value of the input box, using the document object method:<br>
<span style="font-family:font-family: Courier, monospace;">getElementById().value;</span></br>
The value is whatever is written in the input box.<br>
This value is then stored it in a variable (using the key word var) called “yourName”.<br>
The function then adds the value of the variable after the word “Hello”, using the + operator, and
writes it to the document.<br>
Adding two string (word) values together with the ‘+’ operator is known as ‘concatenation’.<br>
Exercise: Modify the output text so that it adds “How are you?” after the user’s name.
</p>

<hr>
<p><strong>But what happens if the user doesn't enter a name?</strong></p>
<p>Yes, that's right, you get a message saying only 'Hello' with no name.</p>
<p>We can solve this by making sure the user enters a name:</p>

<p>Enter your name: <input type="text" id="inputName2"><button onclick="test4()">Try it</button></p>
<p>The message will appear here: <span id="output2"></span></p>
<script>
function test4() {
  var yourName = document.getElementById("inputName2").value;
  if(!yourName){
  alert("Please enter your name!");
  }
  else {
  document.getElementById("output2").innerHTML = "Hello " + yourName;
  }
}
</script>

<p>The script</p>

```
<p>Enter your name: <input type="text" id="inputName2"><button onclick="test4()">Try it</button></p>
<p>The message will appear here: <span id="output2"></span></p>

<script>
function test4() {
  var yourName = document.getElementById("inputName2").value;
  if(!yourName){
  alert("Please enter your name!");
  }
  else {
  document.getElementById("output2").innerHTML = "Hello " + yourName;
  }
}
</script>
```

<h3>Explanation</h3>
<p> 
JavaScript provides a core programming construct known as 'if' condition. We can use an ‘if’ condition to check that the text box contains a value.<br>
Look at the ‘if’ and ‘else’ conditions in the code above: The ‘if’ statement checks whether the variable ‘name’ contains a value. This is done using Boolean NOT operator (!), placed before the variable name. In plain English, this means: ‘if the variable ‘yourName’ is empty (i.e. if !yourName is true), show an alert box.<br>
The if statement is followed by an else statement, which executes if the first ‘if’ statement is false. In this case, the ‘else’ statement writes the value to the document.
</p>


