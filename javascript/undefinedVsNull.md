# undefined vs null

According to google: 

> undefined means a variable has been declared but has not yet been assigned a value. On the other hand, null is an assignment value. It can be assigned to a variable as a representation of no value. Also, undefined and null are two distinct types: undefined is a type itself (undefined) while null is an object.

Let's see if this guy is telling the truth:

```
console.log(typeof null) // 'object'
console.log(typeof undefined) // 'undefined'
```

Nice!

We can have a null reference only if we have already declared it. In other words, JavaScript never sets a value to null. That must be done programmatically:

```javascript
    var a = null;
    console.log(a === null); //true
```

A very important thing is that undefined is not the same not defined.

```javascript
var a;
console.log(a) // undefined
console.log(b) // Uncaught ReferenceError: b is not defined
```

undefined means a variable **has been declared** but has not yet been assigned a value. 

While doing test I realized that an undefined value can be equal (but not strict equal) to null.

```javascript
var a;
console.log(a == null) // true
console.log(a == undefined) // true
```

Then we can say that null == undefined:

```
console.log(null == undefined) // true
```

This happens because we are using the non-strict operator (==) and we are evaluating only the reference, wich is empty.

If we strict compare null with undefined we get:

```
console.log(null === undefined) // false
```

This is because undefined's type is 'undefined' and null's type is 'object'

In my opinion:

Null is used to programmatically say that something is empty. Undefined is used to say that the reference is not existing. 
