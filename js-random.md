---
layout: default
title: js random
---

<h1>JavaScript Random Text Examples</h1>
<p>This page demonstrates how you can use JavaScript to display randomised text.</p>

<h2>Example 1</h2>
<p>This example demonstrates a simple random(ish) sentence generator, using subject + verb + adverb patterns.</p>
<p>Clicking the button below will display a list of subjects (names and pronouns) followed by a verb and adverb. Each time you click the button, the verbs and adverbs will vary for each subject (within the limit of the number of available verbs (5)). </p>
<p>Examine the code below to see how it's done:</p>

<button id="btn1">Make sentences</button>
<p>Click the button more than once to see the sentences change. Random sentences will appear below here.</p>
<p id="demo"></p>

<script>
btn1.addEventListener("click", makeSentence);

function makeSentence() {

var person = {
    names: [ "Brian", "Betty", "Fiona", "Freddy", "Mini", "Marvin", "Alice", "Bob", "Jane", "Arthur", "Vincent", "Amy", "He", "She" ],
    verbs: [ "speaks", "eats", "runs", "walks", "drinks" ],
    adverbs: ["slowly", "quickly", "nicely", "noisily", "a lot", "a little", "rarely" ]
   
};

var i;
var text = "";
for (i = 0; i < person.names.length; i++) {

  name = person.names[i];
  verb = person.verbs[Math.floor(Math.random() * person.verbs.length)];
  adv = person.adverbs[Math.floor(Math.random() * person.adverbs.length)]; 
  text += name + " " + verb + " " + adv + "<br>";
  document.getElementById("demo").innerHTML = text;
 }  
}
</script>

<h3>The Code</h3>
<p>Note: You need a button with id "btn1" for this script call. You will also need a paragraph element with id="demo" below the button. </p>

```
<script>
btn1.addEventListener("click", makeSentence);
function makeSentence() {

var person = {
    names: [ "Brian", "Betty", "Fiona", "Freddy", "Mini", "Marvin", "Alice", "Bob", "Jane", "Arthur", "Vincent", "Amy", "He", "She" ],
    verbs: [ "speaks", "eats", "runs", "walks", "drinks" ],
    adverbs: ["slowly", "quickly", "nicely", "noisily", "a lot", "a little", "rarely" ]
   
};
  
var i;
var text = "";
for (i = 0; i < person.names.length; i++) {

  name = person.names[i];
  verb = person.verbs[Math.floor(Math.random() * person.verbs.length)];
  adv = person.adverbs[Math.floor(Math.random() * person.adverbs.length)]; 
  text += name + " " + verb + " " + adv + "<br>";
  document.getElementById("demo").innerHTML = text;
 }  
}
</script>
```

<h3>Explanation</h3>
<p>The code above introduces three important programming constructs: Objects, Arrays and Loops; and the JavaScript Math Method.</p>
<p>The first code block in the function is a variable object <code> var </code> named 'person'. The person object is assigned a series of properties: <code> names </code>, <code> verbs </code> and <code> adverbs </code>. Each of these properties contains multiple possible values, which are listed inside square brackets <code>[ ]</code>. This type of variable list is known as an Array object. An array object contains multiple values. Each value inside the array can be referenced by an index number. For example, <code> person.names[0] </code> will return 'Brian'.</p>
<p>The next block of code is the Loop structure. In this example, the loop structure has a counter variable named 'i', which is set to zero <code> i=0 </code>. The next parameter of the loop states how many times the loop should run <code> i < person.names.length </code>. This means that the loop will count the number of names in the names list at set this as the number of times the loop should run. So, as long as i is less than that number, the loop will run. Each time the loop runs, 1 is added to i <code> i++ </code>. When i = the number of names in the list, it will stop running.</p>
<p>Inside the loop, the code gets random items from the verbs and adverbs arrays, using the Math function. I won't go into this here.</p>
<p>The only point you need to understand at this stage is that you can modify the terms in the array lists and the code will work. So you can add new names, change the names, add new verbs and adverbs etc. Try it and see.</p>
<hr>

<h2>Example 2</h2>
<p>In this example, I demonstrate how to load a random idiom when the page loads or when the button is clicked.</p> 
<p>The same procedures as above have been deployed, but instead of looping through the entire list of items, the code simply accesses any one of the items and displays it on the page.</p>
<p>Click the button or refresh the page to see another sentence displayed.</p>

<h2>Random colour idiom</h2>
<dl id="quote"></dl>
<!--<script src="script.js"></script>-->
<button id="btn2">See another random idiom</button>
<hr>

<script>
var idioms = [ 
'Once in a blue moon = very rarely.', 
'Tickled pink = to be extremely pleased.', 
'Caught red-handed = to catch someone in the act of doing something.',    
'White lie = a small lie that is told to be polite or avoid hurting someone’s feelings.',
'Feel blue = Be depressed or sad. The use of blue to mean “sad” dates from the late 1300s.',
'See red = Become very angry suddenly.'
];

var examples = [
'Example: <i>Once in a blue moon you will see that mean professor smile.</i>', 
'Example: <i>Your grandma was tickled pink that you called on her birthday!</i>', 
'Example: <i>He was caught red-handed while stealing those biscuits.</i>',
'Example: <i>I didn’t like her dress, but I told a white lie because I didn’t want to offend her.</i>',
'Example: <i>I was really feeling blue after she told me she was leaving.</i>',
'Example: <i>The thought of Piers with Nicole made her see red.</i>'

];

var quoteNo;
var idiomNo;
btn2.addEventListener("click", loadQuote);
function loadQuote() {
    idiomNo = Math.floor(Math.random() * (idioms.length));
    if(idiomNo !== quoteNo) {
    //alert(quotes[quoteNo]);
    	document.getElementById("quote").innerHTML = "<dt>" + idioms[idiomNo] + "</dt>" + "<dd>" + examples[idiomNo] + "</dd>";
   	quoteNo = idiomNo;
    	return quoteNo;
    	}
    	else {
    	loadQuote();
    	}
	}
loadQuote();
</script>

<h3>The code:</h3>
<p>Note: For this example you need a button with id "btn2" for this script call. You will also need this page element above the button: &lt;dl id="quote"&gt;&lt;/dl&gt;</p>
	

```
<script>
var idioms = [ 
'Once in a blue moon = very rarely.', 
'Tickled pink = to be extremely pleased.', 
'Caught red-handed = to catch someone in the act of doing something.',    
'White lie = a small lie that is told to be polite or avoid hurting someone’s feelings.',
'Feel blue = Be depressed or sad. The use of blue to mean “sad” dates from the late 1300s.',
'See red = Become very angry suddenly.'
];

var examples = [
'Example: <i>Once in a blue moon you will see that mean professor smile.</i>', 
'Example: <i>Your grandma was tickled pink that you called on her birthday!</i>', 
'Example: <i>He was caught red-handed while stealing those biscuits.</i>',
'Example: <i>I didn’t like her dress, but I told a white lie because I didn’t want to offend her.</i>',
'Example: <i>I was really feeling blue after she told me she was leaving.</i>',
'Example: <i>The thought of Piers with Nicole made her see red.</i>'

];

var quoteNo;
var idiomNo;
btn2.addEventListener("click", loadQuote);
function loadQuote() {
    idiomNo = Math.floor(Math.random() * (idioms.length));
    if(idiomNo !== quoteNo) {
    //alert(quotes[quoteNo]);
    	document.getElementById("quote").innerHTML = "<dt>" + idioms[idiomNo] + "</dt>" + "<dd>" + examples[idiomNo] + "</dd>";
   	quoteNo = idiomNo;
    	return quoteNo;
    	}
    	else {
    	loadQuote();
    	}
	}
loadQuote();
</script>

```

<hr>
<p>That's it for this demonstration of JavaScript Arrays, loops and math functions</p>
