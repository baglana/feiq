# feiq

1. What will be printed to the console?
```js
  let a = 10;
  a.b = 10;
  console.log(a);
```
<details>
 <summary>Output</summary>
   10
</details>

2. What storages do save data after closing the browser? (`LocalStorage`, `CookieStorage`, `SessionStorage`)
3. ```js
   Promise.reject('a')
    .catch(p => p + 'b')
    .catch(p => p + 'c')
    .then(p => p + 'd')
    .finally(p => p + 'e')
    .then(p => console.log(p))
   ```
<details>
 <summary>Output</summary>
   abd
</details>

4. What is the function's `[[Scope]]` property equal to?
    1. Current Lexical Environment
    2. Current Lexical Environment or window
    3. Function doesn't have such property
    4. Lexical Environment in which this function was called

5. What is `HTMLCollection`?
    1. An object with numeric keys containing DOM elements and provides additional methods for working with the collection
    2. Array of DOM elements
    3. Array of DOM elements, that has additional methods to work with this collection
    4. An object with numeric keys containing DOM elements and provides methods for working with them like with an array
  
6. What will be printed to the console?
```js
var a = 'hello';
function b() {
    if (false) {
        var a = 'world';
    } else {
        var b = 'man';
    }
    console.log(b);
    console.log(a);
}
b();
```
<details>
 <summary>Output</summary>
   man, undefined
</details>

7. What will be printed to the console?
```js
const map = new Map();

map.set('0', '1');
map.set('s2', '2s');
map.set('3s', 's3');

const arr = [...map.values()];
const result = arr.map(value => parseInt(value, 10));

console.log(result);
```
<details>
 <summary>Output</summary>
    [1, 2, NaN]
</details>

8. What will be printed to the console?
```js
var x = 10

function bar(funArg) {
    var x = 30;
    funArg();
}

function foo() {
    console.log(x)
}

foo.x = 20;
bar.x = 40;

bar(foo);
```
<details>
 <summary>Output</summary>
  10
</details>

9. What will be printed to the console?
```js
var obj = {
    a: () => {
        console.log(this.prop);
    },
    prop: 1
};

obj.a();
var fn = obj.a.bind(obj);
fn();
```
<details>
 <summary>Output</summary>
  undefined, undefined
</details>

10. What will be printed to the console if we click three times?
```js
class GODListener {
  constructor() {
      this.counter = 0;
  }

    handleClick() {
        this.counter += 1;
        console.log(this.counter);
    }
}

const element = document.getElementById('testBtn');
const listener = new GODListener();

element.addEventListener('click', listener.handleClick);
```
<details>
 <summary>Output</summary>
  NaN, NaN, NaN
</details>

11. What will be printed to the console?
```js
var a = {};
(function b(a) {
    a.a = 10;
    a = null;
})(a);
console.log(a);
```
<details>
 <summary>Output</summary>
  { a: 10 }
</details>
