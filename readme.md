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

Here is [JsFiddle](https://jsfiddle.net/23LupeLk/) to show you the repro.
