---
# This file is best viewed in vscode using vscode-reveal
# https://marketplace.visualstudio.com/items?itemName=evilz.vscode-reveal
title: "Sync Functions"
logoImg: "https://raw.githubusercontent.com/HansUXdev/JavaScript-First/2acf5840c15af96602aceb66303ea69c5b75e344/logo.svg"
theme: "night"
highlightTheme: "Monokai"
#transition: " slide "
#transitionSpeed: " default " 
#slideNumber: true
#loop: true
#autoSlide: 5000 
# openButton: false
#enableMenu: false
# controlsLayout: 'edges'
# controls: true
#enableChalkboard: false
# enableTitleFooter: false
#autoSlideStoppable: true
---

<link rel='stylesheet' href='theme.css'>
<style>
</style>


### Synchronous Functions

1. Function Declaration
2. Function Expression
3. Anonymous Functions
4. Arrow Functions
5. Curried Function
6. Closure
7. IFFE

--

#### **[Function Declaration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)** VS **[Function Expression](https://developer.mozilla.org/en-US/docs/web/JavaScript/Reference/Operators/function#:~:text=A%20function%20expression%20is%20very,expressions%20to%20create%20anonymous%20functions.)** :

This is a **Function DECLARATION**, {.fragment .current-only data-code-focus=1-3}

This is a **Functions EXPRESSION** {.fragment .current-only data-code-focus=5-6 }

This is a **ANONYMOUS Functions** {.fragment .current-only data-code-focus=7-8 }

<div class="flex-slide">

:::block


```JavaScript
function add(param1, param2){
  return param1 + param2;
};
add(1, 2) //returns a value of 3
// Expression
const name = function(){/*Code Block*/}
// Anonymous Functions
function(){ /*Code Block*/ }
```

{.column}
:::

:::block
<!-- Has the following Features: -->

**Block Syntax**, with `{}` at the begining and the end of the function and usually followed by a `;` {.fragment .current-only data-code-focus=1-3}


* **Function** keyword {.fragment .current-only data-code-focus=1-1}
* Name of function, `add` is on the right of the function keyword {.fragment .current-only data-code-focus=1-1}
* Parameters `(param1, param2)`, which act as variables inside the functions definition. {.fragment .current-only data-code-focus=1-1}


**Return** keyword, ends the function
and the result is returned {.fragment .current-only data-code-focus=2-2}

* Function must be called before it runs {.fragment .current-only data-code-focus=4-4}

* When the function is called, we pass values into the **arguements** `(1,2)` {.fragment .current-only data-code-focus=4-4}

* When the function is called, we pass values into the **arguements** `(1,2)` {.fragment .current-only data-code-focus=1-2}

<!-- Function Expression -->

The main difference is where the function `name` is place. {.fragment .current-only data-code-focus=5-5 }

The function `name` is placed on the left hand side of the `function` keyword. {.fragment .current-only data-code-focus=5-5 }

In an Expression, the name can be ommitted in order to make it **Anonymous** {.fragment .current-only data-code-focus=7-8 }

This usually used as a callback or inside and IFFE. {.fragment}

<!-- Anonymous Functions  -->
This usually used as a callback or inside and IFFE. {.fragment}

{.double-column}
:::

</div>

--

### [Arrow](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) Functions 

```javascript
  // named arrow function
  const name = (params) => {
    console.log(params,"named");
  }
  // multiline
  () => {
    console.log("multiline");
  }
  // single line
  (a,b,c) => console.log("single");
  a => console.log(a);
```

This is an **expression** using an arrow function expressin {.fragment .current-only data-code-focus=1-4 }

This is the **Anonymous** version. {.fragment .current-only data-code-focus=5-8 }

The `()` are used for multiple parameters and the `{}` can be ommitted. {.fragment .current-only data-code-focus=10-10 }

The `()` can be ommitted. {.fragment .current-only data-code-focus=11-11 }

--

### [IIFE](https://developer.mozilla.org/en-US/docs/Glossary/IIFE) (Immediately Invoked Function Expression)

```javascript
  // ()()
  // (function(){})()
  // (()=>{})()
  (
  function () {
    var foo = "bar";
    console.log(foo);
  }
  )
  ();
```

We start with two parentheses `()()`. {.fragment .current-only data-code-focus=1-1 }

Then add an anonymous function, inside the first `()`.  {.fragment .current-only data-code-focus=2-3 }

--

<!-- This example is straight from MDN -->

### [Closure](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures) 
is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment).

```javascript
function init() {
  var name = 'Mozilla'; 
  function displayName() { 
    alert(name); 
  }
  displayName();
}
init();
```
 `name`  is function scoped to the function `init()` {.fragment .current-only data-code-focus=2-2 }
 
 displayName() is the inner function, a closure {.fragment .current-only data-code-focus=3-5 }

 using the `name` variable which is in the parent function, `init()` {.fragment .current-only data-code-focus=4-4 }

--

### [Currying](https://javascript.info/currying-partials) 
is a transformation of functions that translates a function from callable as `f(a, b, c)` into callable as `f(x)(y)(z)`.
 
```javascript
function closureScoped(job) {
  if (job=="student") {
    return (name) => console.log(`my name is ${name} my job is study this code`) 
  }
  else if (job=="teacher") {
    return (name) => console.log(`my name is ${name} my job is ${job}`) 
  }
  else {
    return () => console.log(`I'm not paying attention because my job is ${job}`) 
  }
}
closureScoped("designer")("hans");
```
 The functions checks what the job title is


---