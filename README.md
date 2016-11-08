# javascript-interview-questions-i-ask
JavaScript Fundamentals questions I ask during an interview.

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
    this.jsLevel = attribute.jsLeve || 0
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
1. What is the most specific and direct way to select the button given the DOM structure below? (You may utilize jQuery)
  ```html
  <section id="container">
    <h2>Awesome Website</h2>
    <p>This is some text ...</p>
    <div id='layer1'>
      <h3>Some more text</h3>
      <span id='layer2'>
        <input type='text' name='someTextInput'/>
        <span id='layer3'>
          <i class='icon'>Icon</i>
          <div class='special-styles'>
            <button class="clickable">Target</button>
          </div>
        </span>
      </span>
    </div>
  </section>
  ```
