---
title: JavaScript 30 Day 1
layout: post
author: Rachel Wang
---

#### ⚡ Day 1 Code Snippets from #JavaScript30, You Ready? Here we go!

From the Day 1 exercise, topics that I had to revisit were, Template Literals, Events and Array object. The following snippets are examples from the exercise as well as explanations I found on the web.

### Template Literals

- Template literals are literals delimited with backtick (`) characters. 

In the exercise we see the querySelector populated with ${e.keyCode} a template literal expression.

```
const audio = document.querySelector(`audio[data-key="${e.keyCode}"]`);
```

### Template literals allow the following:
---

#### Multi-line strings

```
// Multi-line strings 
console.log(`string text line 1
string text line 2
string text line 3`);
```

#### String interpolation 

Avoid the concatenation operator by using placeholders of the form `${expression}` to perform substitutions for embedded expressions.

```
let firstName = "Tony";
let lastName = "Stark";
let text = `Welcome ${firstName}, ${lastName}!`; 

let nickel = 5;
let dime = 10;
console.log(`Fifteen cents is ${nickel + dime} and
not ${2 * nickel + dime}.`);


// Output
// "Fifteen cents is 15 and
// not 20."

```

#### Tagged Templates 

- Parse template literals with a function. First argument of a tag function `function uppercase` contains an array of string values `strings` and the remaining arguments `...values` are related to the expressions. 
- In the example below, we'll see the values of variables `name` & `occupation` are changed to uppercase and the remaining strings that are not referenced as expressions are left alone.

```
function uppercase(strings, ...values) {
  let newStr = '';
  for (let i = 0; i < strings.length; i++) {
    if (i > 0) {
      newStr += values[i-1].toUpperCase();
    }
    newStr += strings[i];
  }
  return newStr;
}

let name = 'Tony Stark';
let occupation = 'Being an Avenger';
let sentence = uppercase`Hi! I'm ${ name } and I'm busy at ${ occupation }.`;
console.log(sentence);

// OUTPUT 
// Hi! I'm TONY STARK and I'm busy at BEING AN AVENGER.

```

[Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)

---

#### Events 

- Events are fired inside the browser window and attached to a specific item that resides in it. 
- To react to an event, you attach an event handler/event listener to it (JS code that runs when event fires).
- When JavaScript code is defined to run in response to an event, it is registering an event handler.

```
// listen if key is pressed (keydown) then the function playSound event handler/listener 
// will handle the event when the keydown event is fired.
window.addEventListener('keydown', playSound);

//e event 
function playSound(e){
    const audio = document.querySelector(`audio[data-key="${e.keyCode}"]`);
    const key = document.querySelector(`.key[data-key="${e.keyCode}"]`);
    if (!audio) return;
    
    key.classList.add('playing');
    audio.currentTime = 0;
    audio.play();
}
```

---

#### Array Object - forEach

- forEach() method executes a provided function once for each array element.
- In the example, for each key pressed, the event listener function will run when the key press event is fired.

```
const keys = Array.from(document.querySelectorAll('.key'));
keys.forEach(key => key.addEventListener('transitionend', removeTransition))
window.addEventListener('keydown', playSound);
```
[Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

---

Wow! That was quite a bit of learning! Glad we've learned so much after Day 1 exercises. See you in the next one! 🎉