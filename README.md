# JavaScript Debugging.... <img width="30px" src="https://user-images.githubusercontent.com/49618856/188256218-8953c787-cadb-415c-a9f6-24ebbbdd1f88.png">

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

console.time('Adding New Book')
addNewBook(book)
console.timeEnd('Adding New Book')

```
<img width='400px' src="https://user-images.githubusercontent.com/49618856/188258075-7bec08b2-429c-482f-81e6-0f838b149ab6.png"/>

</div>
