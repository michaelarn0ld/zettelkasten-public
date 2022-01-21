# Async/Await vs Promise.prototype.then()
```await``` is just an internal version of ```.then()```; however, using the
former gives the interpretter more opportunities to optimize things internally.

One of the other ***critical*** differences between the two is that ```await```
is mechanically more similar to synchronous programming; it is used to wait
for the resolution or rejection of a ```Promise```. In this way, code below the
```await``` will not excecute until the ```Promise``` fufills.

The ```.then()``` branches off; it attaches the asynchronous function (and its
callback) to the runtime, continues execution in its current scope, and then
executes the callback when the ```Promise``` is fufilled.

Consider the following:
```js
// imagine that call is a function that is fetching data from an API
function call(timeout) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log(`This call took ${timeout} seconds`);
      resolve(true);
    }, timeout * 1000);
  });
}
```
With ```async/await```
```js
(async () => {
    await call(5); // This will print result first
    await call(2);
    await call(1);
})();
```
Console:
```
This call took 5 seconds
This call took 2 seconds
This call took 1 seconds
```
With ```.then()```
```js
(async () => {
    call(5).then(r => console.log(r)) // This will print last
    await call(2);
    await call(1);
})
```
Console:
```
This call took 2 seconds
This call took 1 seconds
This call took 5 seconds
```


***ALWAYS ENSURE PROPER ERROR HANDLING WHEN USING ASYNCHRONOUS FUNCTIONALITY***

## Related
[202110200316](../202110200316) - Types in JavaScript \
[202201191736](../202201191736) - Create a React applcation without create-react-app \
[MDN Async/Await](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Async_await) \
[Helpful Stack Overflow Discussion](https://stackoverflow.com/questions/54495711/async-await-vs-then-which-is-the-best-for-performance)

## Tags
#webdev #javascript
