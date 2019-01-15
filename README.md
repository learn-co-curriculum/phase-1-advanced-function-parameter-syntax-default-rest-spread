# Default / Rest / Spread as Function Arguments

## Learning Goals

- Use JavaScript's default function argument as a parameter in a function
- Use JavaScript's `rest` parameter as a parameter in a function
- Use JavaScript's `spread` operator as a parameter in a function

## Introduction

ES2016 has brought a number of improvements to parameters that we can pass into
functions. Unlike most modern programming languages like Ruby or Python,
JavaScript didn't have a way to pass a default parameter into a function.
However, with the introduction of ES2016, that is no longer the case. It also
introduced two other helpful parameters, the `rest` parameter and the `spread`
operator. In this lab, we're going to learn about and practice using all three. 

## Use JavaScript's default function argument as a parameter in a function

Let's say you work for an e-commerce site, and you're prepping for your
post-holiday sales. You're working on some code for your website and you need to
set a discount of 25% across the board for everything that you sell on the
website. We have a function that takes in an `item` as a price in dollars and a
`discount` as a percentage, and returns the total amount due. 

```js
function sellStuff(item, discount){
    return item - (item * discount)
}
```

Since normally our discounts are on a per-item basis, this code functions great.
But it could be a tiny bit more efficient now that we're going to be setting a
25% off across the board discount. We can set a default 25% off discount by
making a tiny change in our code like this:

```js
function sellStuff(item, discount = 0.25){
    return item - (item * discount)
}
```

Now, if we don't pass in a parameter for our discount, JavaScript will assume
that we want to apply a 25% off discount and calculate it appropriately for us. 

What happens if we had three variables, but didn't want to specify the second
variable?

```js
function sellStuff(item, discount = 0.25, tax){
    return item - (item * discount)
}
```

If we have more than two variables and we want to take advantage of the default
value in our function, but specify the third variable, simply pass in
`undefined` for the second variable, and JavaScript will use our specified
default value. 

**Note: Arrow functions do not have default arguments.**

## Use JavaScript's `rest` parameter as a parameter in a function

You might have heard a little bit about JavaScript's magical "three dots". These three
dots allow you to do two very different things - the `rest` parameter and the
`spread` operator. The `rest` parameter allows you to collect the `rest` of your
remaining parameters that you are passing into your function into an array,
while the `spread` operator allows you to pass elements of an array into a
function as an argument.

Sometimes, we might not know exactly how many arguments we want to pass into a
function, but we might know that we only want to do something with the first two
arguments. In JavaScript, it's possible to pass in any number of arguments into
a function. 

```js

function muppet_lab(a,b){
  console.log(a,b) // Dr. Bunson Beaker
}

muppets("Dr. Bunson", "Beaker", "Miss Piggy", "Kermit", "Animal")
```

But what happens if we want to capture the rest of the arguments
that are left over? The `rest` parameter allows us to take the rest of the
arguments that we pass into the function, and gather them into an array. Here's
how this works:

```js
function muppet_lab(a, b, ...muppets) {
  console.log(x, ' ', y); // Dr. Bunson Beaker

  console.log(muppets); // ["Miss Piggy", "Kermit", "Animal"]
  console.log(muppets[0]); // Miss Piggy
  console.log(muppets.length); // 3
}

muppets("Dr. Bunson", "Beaker", "Miss Piggy", "Kermit", "Animal")
```

Since the `rest` parameter gathers the rest of the parameters given to a
function, it should always come at the end of a list of parameters. 

## Use JavaScript's `spread` operator as a parameter in a function

With the `rest` operator, JavaScript allowed us to put the remaining arguments
into an array. The `spread` operator allows us to pass elements of an array into
a function as an argument. Try it out in console with a simple add function:

```js
function add(a, b, c) {
  return a + b + c ;
}
const arr = [1, 2, 3];

add(...arr); // returns 6
```

So what's happening here? We have a simple add function, with three arguments,
and we are passing in an array using the `spread` operator. The function is
adding all three numbers contained within the array. Play around with it using a
bigger array and see what happens when the array has more numbers than our
function has parameters. 

## Instructions

- Have students write functions using default arguments, rest parameters, and spread operators

## Conclusion

Since the syntax here is similar, how do we know when JavaScript is using the
`spread` operator and when it's using the `rest` parameter? It's all about
context. If the three dots occur when you are calling the function, then it's
the `spread` operator. If they happen when you're defining the function, it's
the `rest` parameter. Don't forget to use default parameters when you have an
argument that you are going to be defining on a regular basis to increase your
code efficiency! 

## Resources

[Default parameters]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters
[Rest parameters]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters
[Spread operators]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax