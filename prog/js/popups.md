## Popups do Javascript

### Alert
```js
window.alert("sometext");

alert("I am an alert box!");
```
### Confirm
```js
window.confirm("sometext");

if (confirm("Press a button!")) {
  txt = "You pressed OK!";
} else {
  txt = "You pressed Cancel!";
} 
```
## Prompt
```js
window.prompt("sometext","defaultText");

var person = prompt("Please enter your name", "Harry Potter");

if (person == null || person == "") {
  txt = "User cancelled the prompt.";
} else {
  txt = "Hello " + person + "! How are you today?";
} 
```
