```js
let a = {
	b: 1,
};
function f(a) {
	a.b = 2;
	console.log(a); // { b: 2 }
}
f(a);
console.log(a); // { b: 2 }
```
______________________________________________
```js
'2' > 1 // true
'01' == 1 // true
true === 1 // false
false == 0 // true
```
______________________________________________
```js
var a = {b: 1};
c = Object.create(a);
console.log(c.b); // 1
delete c.b;
console.log(c.b); // 1
delete a.b;
console.log(c.b); // undefined
a.z = 2;
console.log(c.z); // 2
c.z = 3;
console.log(a.z); // 2
```
______________________________________________
```js
setTimeout(function timeout(){
    console.log('Таймаут') // 5
}, 0);

let p =new Promise(function(resolve, reject){
    console.log('Создание промиса'); // 1
    resolve();
})

p.then(function(){
    console.log('Обработка промиса 1'); // 3
})

p.then(function(){
    console.log('Обработка промиса 2'); // 4
})

console.log('Конец скрипта'); // 2
```
______________________________________________
```js
Promise.resolve()
    .then(() => {
        return "1";
    })
    .finally(data => { 
        console.log(data); // undefined
        return "2";
    })
    .then(data => console.log(data)) // '1'
```
______________________________________________
