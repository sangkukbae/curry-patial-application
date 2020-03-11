# Currying-Patial-Application

## Definitions
`Currying`: the technique of transforming a function that takes multiple arguments in such a way that it can be called as a chain of functions each with a single argument.   
```bash
f(x, y, z) => R
curriedf(x) => g(y) => h(z) => R
curriedf(x)(y)(z).
```
`Partial Application`: the process of fixing a number of arguments to a function, producing another function of smaller arity.   
```bash
f(x, y, z) => R
g(y, z) => R    <=>    f(1, y, z) => R
h(z) => R    <=>    f(1, 2, z) => R
```

**Examples**
```javascript
// original function that takes three parameters a1, a2 and a3
function f(a1, a2, a3) {
    return a1 + a2 + a3;
}
 
// curried function which takes one parameter at a time
function curry(a1) {
    // each stage takes another parameter and get you closer to the
    // full application of f
    return function (a2) {
        // but only with the inner most function do you actually get
        // the return value you wanted
        return function (a3) {
            return f(a1, a2, a3);
        };
    };
}
 
// partial applied function which takes one parameter and fixes
// the other 2
function partial(a1) {
    // a partially applied function of the original function f can
    // get you the full application straight away
    return f(a1, 5, 10);
 
}
 
curry(1)(5)(10); // returns 16
partial(1); // returns 16
```

:memo: **참고 자료**
* [https://theburningmonk.com/2011/01/currying-vs-partial-application/](https://theburningmonk.com/2011/01/currying-vs-partial-application/)   
* [https://towardsdatascience.com/javascript-currying-vs-partial-application-4db5b2442be8](https://towardsdatascience.com/javascript-currying-vs-partial-application-4db5b2442be8)   
* [https://medium.com/@kevincennis/currying-in-javascript-c66080543528](https://medium.com/@kevincennis/currying-in-javascript-c66080543528)   
* [https://medium.com/javascript-scene/curry-or-partial-application-8150044c78b8](https://medium.com/javascript-scene/curry-or-partial-application-8150044c78b8) :heavy_check_mark:   
* [https://medium.com/javascript-scene/curry-and-function-composition-2c208d774983](https://medium.com/javascript-scene/curry-and-function-composition-2c208d774983)   
* https://2ality.com/2011/09/currying-vs-part-eval.html](https://2ality.com/2011/09/currying-vs-part-eval.html)   
* [https://programmingwithmosh.com/javascript/currying-vs-partial-application/](https://programmingwithmosh.com/javascript/currying-vs-partial-application/)   
* [https://www.digitalocean.com/community/tutorials/javascript-functional-programming-explained-partial-application-and-currying](https://www.digitalocean.com/community/tutorials/javascript-functional-programming-explained-partial-application-and-currying)   
* [https://www.youtube.com/watch?v=DzLkRsUN2vE](https://www.youtube.com/watch?v=DzLkRsUN2vE)

