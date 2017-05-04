# javascript-interview-questions-i-ask
JavaScript Fundamental questions I ask during an interview.

## Fundamental JavaScript Exercise

1. What is the difference between undefined and not defined in JavaScript?

1. What is the output?
  ```js
  var y = 1;
  if (function f(){}) {
    y += typeof f;
  }
  console.log(y);
  ```
1. What is a “closure” in JavaScript? Provide an example

1. What is pass by value and pass by reference?

1. What is the difference between the function declarations below?

  ```js
  var foo = function(){
    // Some code
  };
  ```
  **vs**
  ```js
  function bar(){
    // Some code
  };
  ```
1. What is the output for the code below?
  ```js
  $.ajax({
    method: 'GET',
    url: '/foo'
  })
  .done(function(response) {
    console.log('done callback response', response)
  })

  console.log('outside response', response)
  ```
1. If the jsLevelUp() was called, why would it lead to an error? How could it be fixed?
  ```js
  var jamie = new User({
    id: 1,
    name: 'jamie',
    gender: 'other',
    jsLevel: 1
  })

  jamie.jsLevelUp()
  /*
    After calling jsLevelUp() it will cause the following error:

    jsLevel is not defined for jQuery
  */

  function User(attribute) {
    this.id = attribute.id || null
    this.name = attribute.name || ''
    this.gender = attribute.gender || ''
    this.jsLevel = attribute.jsLevel || 0
  }

  User.prototype.jsLevelUp = function() {
    var id = this.id
    $.ajax({
      method: 'PUT',
      url: '/users/' + id
    })
    .done(function(response) {
      /* HINT it has to do with this line */
      this.jsLevel = response.jsLevel
    })
  }
  ```
1. What does this do and why would it be useful?
  ```js
  (function() {
    console.log('I am self invoking')
  })()
  ```
  
1. Implement the following function `add(num1)(num2)`. For example: `add(1)(1)` = 2

1. Write a function that prints out the amount of times it has been invoked.
