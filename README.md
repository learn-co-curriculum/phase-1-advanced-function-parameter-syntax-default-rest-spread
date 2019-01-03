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

Let's say you work for an e-commerce site, and you're prepping for your post-holiday sales. You're working on some code for your website and you need to set a discount of 25% across the board for everything that you sell on the website. We have a function that takes in an `item` as a price in dollars and a `discount` as a percentage, and returns the total amount due. 

```js
function sellStuff(item, discount){
    return item - (item * discount)
}
```

Since normally our discounts are on a per-item basis, this code functions great. But it could be a tiny bit more efficient now that we're going to be setting a 25% off across the board discount. We can set a default 25% off discount by making a tiny change in our code like this:

```js
function sellStuff(item, discount = 0.25){
    return item - (item * discount)
}
```

Now, if we don't pass in a parameter for our discount, JavaScript will assume that we want to apply a 25% off discount and calculate it appropriately for us. 

What happens if we had three variables, but didn't want to specify the second variable?

```js
function sellStuff(item, discount = 0.25, tax){
    return item - (item * discount)
}
```

If you have more than two variables and you want to take advantage of the default value in your function, but specify the third variable, simply pass in `undefined` for the second variable, and JavaScript will use your specified default value. 

**Note: Arrow functions do not have default arguments.**

## Use JavaScript's `rest` parameter as a parameter in a function

## Use JavaScript's `spread` operator as a parameter in a function

## Instructions

- Have students write functions using default arguments, rest operators, and spread operators

## Conclusion

## Resources
