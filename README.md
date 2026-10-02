## Functions

**What a function is**

A function is a reusable block of code that performs a task — define it once, run it (call it) as many times as needed, with different inputs each time. This avoids repeating the same logic everywhere.

**Function declaration — the basic form**

```jsx
function greet() {
  console.log("Hello!");
}

greet();   // calling/invoking the function → prints "Hello!"
greet();   // can call it again, as many times as needed
```

Defining a function doesn't run it — nothing happens until you *call* it (with `()`).

**Parameters and arguments**

```jsx
function greet(name) {
``````jsx
  console.log("Hello, " + name);
}

greet("Mohit");   // "Hello, Mohit"
greet("Riya");    // "Hello, Riya"
```

- `name` in the function definition is a **parameter** — a placeholder
- `"Mohit"` when calling it is the **argument** — the actual value passed in

Multiple parameters:

```jsx
function add(a, b) {
  console.log(a + b);
}

add(5, 3);   // 8
```

**Return values — sending a result back**

```jsx
function add(a, b) {
  return a + b;
}

``````jsx
let result = add(5, 3);
console.log(result);   // 8
```

`return` sends a value back out of the function so it can be stored or used elsewhere. `console.log` inside a function just prints — it doesn't give the value back to use later. `return` does. This distinction trips up a lot of beginners.

```jsx
function multiply(a, b) {
  return a * b;
}

console.log(multiply(4, 5) + 10);   // 30 — the returned value gets used in more code
```

**Code after `return` never runs**

```jsx
function test() {
  return "done";
  console.log("this never runs");   // unreachable
}
```

`return` immediately exits the function.

---

**Default parameters**

```jsx
function greet(name = "Guest") {
  console.log("Hello, " + name);
}

greet();          // "Hello, Guest" — no argument passed, uses default
greet("Mohit");   // "Hello, Mohit" — overrides the default
```**Function expressions — storing a function in a variable**

```jsx
const add = function(a, b) {
  return a + b;
};

console.log(add(2, 3));   // 5
```

Same idea as a function declaration, just assigned to a variable. Difference: this can't be called before it's defined in the code (function declarations can be, function expressions can't — brief mention, not a deep dive today).

**Arrow functions — modern, shorter syntax**

```jsx
const add = (a, b) => {
  return a + b;
};
```Same thing, written with `=>` instead of the `function` keyword.

**Arrow function shortcuts**

```jsx
// implicit return — no {} or "return" needed for single-expression functions
const add = (a, b) => a + b;

// single parameter — parentheses optional
const square = x => x * x;

// no parameters — empty parentheses required
const sayHi = () => console.log("Hi");
```

Arrow functions are used constantly in modern JS, especially with arrays (next week) and React (later in the course) — worth getting comfortable with the syntax now.

---

**Scope — where a variable is accessible**

```jsx
function myFunction() {
  let message = "Hello";
  console.log(message);   // works, inside the function
}

myFunction();
console.log(message);   // ❌ Error — message doesn't exist outside the function
```

A variable declared inside a function only exists inside that function — this is called **local scope**. Variables declared outside any function are in **global scope**, accessible everywhere.

```jsx
let globalVar = "I'm global";

function show() {
  console.log(globalVar);   // works — can read global variables from inside
}

show();
```

**Common mistakes**

- Confusing `console.log` inside a function with `return` — logging shows the value once, `return` lets you actually use it afterward
- Forgetting `()` when calling a function — `greet` refers to the function itself, `greet()` actually runs it
- Trying to access a function's local variable from outside it
- Forgetting `return` in an arrow function written with `{}` — implicit return only works without curly braces

```jsx
const add = (a, b) => { a + b };   // ❌ returns undefined, missing "return"
const add = (a, b) => a + b;       // ✅ correct
```

**Small practice task**# Day-25
js 5 functions**Small practice task**

```jsx
// 1. Write a function "isEven" that takes a number and returns true/false
// 2. Write a function "greetUser" with a default parameter "Guest"
// 3. Convert isEven into an arrow function
// 4. Write a function "calculateArea" that takes width and height, returns the area
// 5. Try logging a variable declared inside a function, from outside it — observe the error
```
