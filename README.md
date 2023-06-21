## 1. What are promises and why do we need them?
Promises are a programming construct used in asynchronous JavaScript to handle the execution of asynchronous operations. They are designed to simplify the handling of asynchronous tasks and provide a structured way to deal with the results or errors that may occur.

In traditional synchronous programming, when a function is called, it blocks the execution of further code until it completes. However, in asynchronous programming, functions are non-blocking, meaning they allow other code to continue running while waiting for a particular task to complete, such as fetching data from a server or reading a file.

Promises act as placeholders for the eventual results of asynchronous operations. They represent a value that may not be available yet but will be resolved at some point in the future. They help in managing asynchronous code by providing a way to handle success or failure when the operation completes.

Here's how promises work:

When an asynchronous operation starts, it returns a promise object immediately. The promise is initially in a pending state.

While the operation is being performed, the promise is said to be "pending." It doesn't block the execution of the code, allowing other tasks to proceed.

Once the operation completes, the promise is either fulfilled with a value (resolved) or rejected with an error. This changes the state of the promise.

When a promise is resolved or rejected, it triggers the execution of the corresponding "callbacks" attached to it. These callbacks are functions provided by the programmer to handle the success or failure of the asynchronous operation.

By using promises, you can chain multiple asynchronous operations together, making the code more readable and easier to reason about. Promises allow you to handle success and failure cases separately, enabling better error handling and avoiding the deep nesting of callbacks, known as "callback hell."
## 2. What is promise chaining
Promise chaining is a technique used to execute multiple asynchronous operations in a sequence, where the output of one operation becomes the input for the next operation. It involves chaining together a series of promises, one after the other, to ensure that they are executed in a specific order.

The basic idea behind promise chaining is that each promise's then() method returns a new promise. This new promise represents the eventual result of the operation specified in the then() callback. By returning a promise from then(), you can attach additional then() callbacks to it, creating a chain of promises.
asyncOperation1()
  .then(result1 => {
    // Process result1 and return a new promise
    return asyncOperation2(result1);
  })
  .then(result2 => {
    // Process result2 and return a new promise
    return asyncOperation3(result2);
  })
  .then(finalResult => {
    // Handle the final result
    console.log(finalResult);
  })
  .catch(error => {
    // Handle any errors that occurred during the chain
    console.error(error);
  });
 
## 3. What is the DOM?
In JavaScript, the DOM (Document Object Model) is a programming interface that represents the web page loaded in a web browser. It provides a way to interact with and manipulate the elements, attributes, and content of the HTML or XML document.

The DOM in JavaScript creates a tree-like structure where each element, attribute, and text node of the document is represented as an object. These objects can be accessed and modified using JavaScript methods and properties, allowing developers to dynamically change the content and behavior of a web page.

By using the DOM, you can perform various operations on web page elements, such as:

Accessing Elements: You can select elements using methods like getElementById(), querySelector(), or getElementsByClassName() to retrieve specific elements from the DOM.

Modifying Content: You can change the text, attributes, or HTML content of elements using properties like textContent, innerHTML, or setAttribute().

Manipulating Styles: You can modify the CSS styles of elements by accessing their style property and setting individual style properties like backgroundColor or fontSize.

Handling Events: You can attach event listeners to elements to respond to user interactions, such as clicks, key presses, or form submissions.

Creating and Deleting Elements: You can dynamically create new elements using methods like createElement() and append them to the DOM. Similarly, you can remove elements using methods like removeChild() or remove().
## 4. What are closures? Give an example of closure
In JavaScript, a closure is a combination of a function and the lexical environment within which that function was declared. It allows a function to retain access to variables and parameters from its outer scope even after the outer function has finished executing. In other words, a closure "closes over" the variables from its outer scope and preserves them.

Here's an example to illustrate closures:
function outerFunction() {
  var outerVariable = 'Hello';

  function innerFunction() {
    var innerVariable = 'World';
    console.log(outerVariable + ' ' + innerVariable);
  }

  return innerFunction;
}

var closure = outerFunction();
closure(); // Output: Hello World
In the example above, outerFunction() defines an outer variable called outerVariable and an inner function called innerFunction(). The innerFunction() has access to the outerVariable due to closure.

When outerFunction() is called and assigned to the variable closure, it returns the innerFunction itself, creating a closure. Even after the execution of outerFunction() is completed, the innerFunction() still retains access to the outerVariable variable.

When closure() is invoked, it logs the concatenated value of outerVariable and innerVariable, which results in "Hello World". The innerFunction() is able to access outerVariable because it forms a closure, preserving the variables from the outer scope.
## 5. How many operators do we have in JS ?
JavaScript has a wide range of operators that serve different purposes and can be categorized into several groups. Here's an overview of the main operator categories in JavaScript:

Arithmetic Operators: These operators are used for performing mathematical operations on numbers, such as addition (+), subtraction (-), multiplication (*), division (/), modulus (%), and exponentiation (**).

Assignment Operators: These operators are used to assign values to variables. Examples include the assignment operator (=), compound assignment operators like addition assignment (+=), subtraction assignment (-=), and so on.

Comparison Operators: These operators compare two values and return a Boolean result (true or false). They include equality (==, ===), inequality (!=, !==), greater than (>), less than (<), greater than or equal to (>=), and less than or equal to (<=).

Logical Operators: These operators are used to combine or manipulate Boolean values. The logical AND (&&), logical OR (||), and logical NOT (!) are commonly used in JavaScript.

Bitwise Operators: These operators perform operations at the binary level on numeric values. They include bitwise AND (&), bitwise OR (|), bitwise XOR (^), bitwise NOT (~), left shift (<<), right shift (>>), and unsigned right shift (>>>).

Unary Operators: These operators work on a single operand. Examples include the unary plus (+), unary minus (-), increment (++), decrement (--), and logical NOT (!).

Conditional (Ternary) Operator: The conditional operator (condition ? expression1 : expression2) is a concise way to write a conditional statement and choose between two expressions based on a condition.
## 6. What are objects in javascript?
In JavaScript, objects are a fundamental data type that allows you to store and organize related data and functions as key-value pairs. Objects are dynamic and flexible, allowing you to create, modify, and access properties and methods at runtime.

An object in JavaScript is a collection of properties, where each property consists of a name (or key) and a corresponding value. The value can be of any data type, including other objects, arrays, functions, and primitive types such as numbers, strings, and booleans.
// Creating an object using object literal notation
var person = {
  name: 'John',
  age: 30,
  city: 'Abc',
  getInfo: function() {
    return this.name + ' is ' + this.age + ' years old and lives in ' + this.city;
  }
};
Objects in JavaScript can also serve as prototypes for creating new objects using constructor functions or the newer class syntax. This allows for object-oriented programming in JavaScript.

Overall, objects in JavaScript are versatile and powerful data structures that facilitate the organization, manipulation, and modeling of complex data and behavior. They are a key component of the language and play a central role in many JavaScript applications and libraries.
