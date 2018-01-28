# Learning from building WebUI

This will be a collection of learnings from building WebUI

## Learning 1: Label inside a container with click handler

If you have a checkbox, the common practice is to have a label that is annoated with "for" attribute set to the name/id of the checkbox. Like below


``` html
<div class='outer'>
  <div class='box'>
    <input type='checkbox' id='check'/><label for='check'>check label</label>
  </div>
</div>
```

However, if you have click handler on the container element, then be careful with preventDefault

``` javascript
$(function() {
  $('.box').click(function(e) {
    e.preventDefault(); // this will break the checkbox and label
    e.stopPropagation();
  })
})
```

Here is [JsFiddle](https://jsfiddle.net/23LupeLk/2/) to show the behavior.

## Learning 2: Dynamic property name in JSON object

If you need to creat json object whose property name is dynamic, put them in array ([]) operators like below

``` javascript
var key = 'toast';
var obj = {
  [key]: 'French'
};
console.log(JSON.stringify(obj)); // ==> { "toast": "French"}
```

Here is [JsFiddle](https://jsfiddle.net/Ln2zkk3h/) to show the work.

## Learning 3: nth-child CSS pseudo selector

```scss
// from 3rd child on
:nth-child(n+3)
// every 3rd child
:nth-child(3n)
// last 2 children
:nth-last-child(-n+2)
// between child 3 and 6
:nth-child(n+3):nth-child(-n+6)

```

Here is [JsFiddle](https://jsfiddle.net/b7z6e201/1/) to show the example above.

