---
layout: default
title: JavaScript Basics
---

<h1>JavaScript Basics</h1>
<p>On this page, you can learn three very basic JavaScript examples, and read through the code extracts and explanations.</p>
<p>You can also copy the code extracts from the grey code boxes and try them on your own website.</p>

<h2>1. A Simple Alert Box</h2>
<p>This example shows a simple alert box when a button is clicked</p>

<button id="myButton">Click me</button>
<script>
myButton.addEventListener("click", test1);    
function test1() {
  alert("Hello! I am an alert box!");
}
</script>

<p>The script:</p>

```

<button id="myButton">Click me</button>
<script>
myButton.addEventListener("click", test1);  
function test1() {
  alert("Hello! I am an alert box!");
}
</script>

```

<h3>Explanation</h3>

<p> 
<ol>
<li>First we have a button with an ID of "myButton" attached. This button is an HTML object and can be placed anywhere on the page.</li>
<li>Next, we have our JavaScript code block, inside the &lt;script&gt; tags.</li>
<li>The first thing the code does is access the object named 'myButton' and attach an event listener to it. The event is "click" and the action performed by the click is the function named 'test1'.</li>
<li>The test1 function is created using the 'function' keyword. The function is named test1(), and it performs the action enclosed within { ... }. This function performs an 'alert()', which presents a pop-up box.</li>
<li>Inside the alert() object we have the sentence "Hello! I'm an alert box!", which will display to the user.</li>
</ol>
</p>

<p><a href="https://www.w3schools.com/jsref/met_win_alert.asp">Reference for this script</a></p>
<hr>

<h2>2. Writing something into a document</h2>
<p>This example shows how JS can manipulate text on a document.</p>
<button id="button2">Click this button and watch the text below change.</button>
<p style="font-weight:bold;" id="demo1">Watch this text change.</p>
<script>
  button2.addEventListener("click", test2); 
  function test2() {
  document.getElementById("demo1").innerHTML = "Hello World! How are you today?";
  }
</script>

<p>The script:</p>

```

<button id="button2">Click this button and watch the text below change.</button>
<p style="font-weight:bold;" id="demo1">Watch this text change.</p>
<script>
  button2.addEventListener("click", test2); 
  function test2() {
    document.getElementById("demo1").innerHTML = "Hello World! How are you today?";
  }
</script>

```

<h3>Explanation</h3>
<ul>
<li>This code illustrates a highly useful JavaScript method for accessing the Document Object. JavaScript uses &lsquo;dot syntax&rsquo; to access this:</li>
</ul>
<p style="padding-left: 60px;"><span style="font-family: font-family: Courier, monospace;">document.getElementById("demo1").innerHTML = </span></p>
<ul>
<li>Notice the dots. This is a JavaScript method for parsing the document in search of an HTML tag with the id &ldquo;demo1&rdquo;.</li>
<li>Once the tag with ID &ldquo;demo1&rdquo; is located, whatever is placed after the = sign is displayed inside the &lt;p&gt; tag of the document.</li>
</ul>

<p><a href="https://www.w3schools.com/jsref/met_document_getelementbyid.asp">Reference for this script</a></p>
<hr>

<h2>3. Extending the above to get user input and output it to the document</h2>
<p>This example shows how JS can take user input and join it to another text and output it.</p>
<p>When you enter a name and submit, a message will be displayed underneath.</p>

<p>Enter your name, or any name: <input type="text" id="inputName"><button id="button3">Submit</button></p>
<p>The message will appear here: <span id="output1"></span></p>

<script>
button3.addEventListener("click", test3); 
function test3() {
  var yourName = document.getElementById("inputName").value;
  document.getElementById("output1").innerHTML = "Hello " + yourName + ". How are you today?";
}
</script>

<p>The script:</p>

```

<p>Enter your name, or any name: <input type="text" id="inputName"><button id="button3">Submit</button></p>
<p>The message will appear here: <span id="output1"></span></p>

<script>
button3.addEventListener("click", test3); 
function test3() {
  var yourName = document.getElementById("inputName").value;
  document.getElementById("output1").innerHTML = "Hello " + yourName + ". How are you today?";
}
</script>

```


<h3>Explanation</h3>
<ul>
<li>An HTML input box with an ID of &ldquo;inputName&rdquo; accepts user input.</li>
<li>The function gets the value of the input box, using the document object method: <span style="font-family: font-family: Courier, monospace;">getElementById().value;</span></li>
<li>The value is whatever is written in the input box.</li>
<li>This value is then stored it in a variable (using the key word var) called &ldquo;yourName&rdquo;.</li>
<li>The function then adds the value of the variable after the word &ldquo;Hello&rdquo;, using the + operator, and writes it to the document.</li>
<li>Adding two string (word) values together with the &lsquo;+&rsquo; operator is known as &lsquo;concatenation&rsquo;.</li>
<li>The script then adds the phrase &ldquo;How are you today?&rdquo; after the user&rsquo;s name.</li>
</ul>


<hr>
<p><strong>But what happens if the user doesn't enter a name?</strong></p>
<p>Try the above example again, without inputting a name. You will see a message saying only 'Hello' with no name.</p>
<p>We can solve this by making sure the user enters a name:</p>

<p>Enter your name: <input type="text" id="inputName2"><button id="button4">Try it</button></p>
<p>The message will appear here: <span id="output2"></span></p>
<script>
button4.addEventListener("click", test4); 
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

<p>Enter your name: <input type="text" id="inputName2"><button id="button4">Try it</button></p>
<p>The message will appear here: <span id="output2"></span></p>

<script>
button4.addEventListener("click", test4); 
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
<p>JavaScript provides a core programming construct known as 'if' condition. We can use an &lsquo;if&rsquo; condition to check that the text box contains a value. Look at the &lsquo;if&rsquo; and &lsquo;else&rsquo; conditions in the code above:</p>
<ul>
<li>The &lsquo;if&rsquo; statement checks whether the variable &lsquo;name&rsquo; contains a value.</li>
<li>This is done using Boolean NOT operator (!), placed before the variable name.</li>
<li>In plain English, this means: &lsquo;if the variable &lsquo;yourName&rsquo; is empty (i.e. if <strong>!yourName</strong> is true), show an alert box.</li>
<li>The if statement is followed by an else statement, which executes if the first &lsquo;if&rsquo; statement is false (i.e., if <strong>yourName</strong> is not empty).</li>
<li>In this case, the &lsquo;else&rsquo; statement writes the value to the document.</li>
</ul>
<hr>
<p>This is the end of this brief introduction to JavaScript.</p>
<hr>
