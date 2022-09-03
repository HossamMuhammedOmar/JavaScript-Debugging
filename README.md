# JavaScript Debugging.... <img width="30px" src="https://user-images.githubusercontent.com/49618856/188256218-8953c787-cadb-415c-a9f6-24ebbbdd1f88.png">


### Code Example
```javascript
const book = {
  name: 'The Magic Duck: JavaScript',
  type: 'Educational',
  pages: 987,
  authors: [
    {name: 'Gary', age: 23},
    {name: 'Moe', age: 26},
    {name: 'Bubba', age: 30},
    {name: 'Gordo', age: 21},
  ]
}
```
<hr/>

<div>

### CONSOLE.LOG

```javascript
console.log(book.authors)

```
<img width="300px" src="https://user-images.githubusercontent.com/49618856/188257121-cfd518f1-0432-4387-a565-3103fa6b6520.png"/>

</div>

<hr/>

<div>

### CONSOLE.TABLE
`The outcome will be displayed on the table. It will come in handy if you try to debug the arrays`
```javascript
console.table(book.authors)

```
<img src="https://user-images.githubusercontent.com/49618856/188257264-b41c5e55-dbbe-44bc-909b-3648bd575bd5.png"/>

</div>

<hr/>

<div>

### CONSOLE.TIME
`You can determine how long it takes your code to execute`
```javascript
/* 
  Let's imagine this function is adding the new book to the API,
  and we want to know if this function is running fast or if we have a performance issue with it.
*/

// You can ignore this function. It is just an example.
function addNewBook(bookObject) {
  fetch('https://duckbooks/education.com/posts', {
  method: "POST",
  body: JSON.stringify(bookObject),
  headers: {"Content-type": "application/json; charset=UTF-8"}
})
.then(response => response.json()) 
.then(json => console.log(json))
.catch(err => console.log(err))
}

// Here is how to calculate the execute time.
console.time('Adding New Book')
addNewBook(book)
console.timeEnd('Adding New Book')

```
<img width='400px' src="https://user-images.githubusercontent.com/49618856/188258075-7bec08b2-429c-482f-81e6-0f838b149ab6.png"/>

</div>

<hr/>

<div>

### CONSOLE.TRACE
`It will show the call stack that exists at the point console.trace was called`
```javascript

function a() {
  // DO something....
  b()
}

function b() {
  // DO something....
  c()
}

function c() {
  // DO something....
  console.trace('trace test')
}

a()

```
<img src="https://user-images.githubusercontent.com/49618856/188258942-5ec61b71-b079-498b-8fc2-6e1a7b8cad78.png"/>

><b>A useful Tutorial:</b> https://www.youtube.com/watch?v=QuO0UDkW2rk&t=278s


</div>

<hr/>

<div>

### debugger
`When you invoke a debugger keyword, it will pause JavaScript execution before executing the following lines of code`
```javascript
function calc() {
  let x = 10 * 50 + 15;
  debugger;
  let y = 10 -20 * 5; 
}
```
<img src="https://user-images.githubusercontent.com/49618856/188259370-3078f080-1ef8-4e6d-a5e3-f1d2f08e3816.png"/>
</div>

<hr/>

<img width="30px" src="https://user-images.githubusercontent.com/49618856/188259592-827202ab-11d0-42db-afc6-7ece555cb7ba.png"/> <img width="30px" src="https://user-images.githubusercontent.com/49618856/188259594-2bdd80a0-1c2d-4dcc-81e4-40df0e0af2f4.png"/> <img width="30px" src="https://user-images.githubusercontent.com/49618856/188259595-651029c6-fb50-4b4f-8f1a-4196644b6d07.png"/> <img width="30px" src="https://user-images.githubusercontent.com/49618856/188259596-bff0235a-b08e-4018-b80a-03d9b2f9e6f4.png"/> <img width="30px" src="https://user-images.githubusercontent.com/49618856/188259597-8068dba8-2d21-4d5e-bbb7-5bf5cf768ee6.png"/>

