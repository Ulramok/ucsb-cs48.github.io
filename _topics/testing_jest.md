---
topic: "Testing: Unit Testing with Jest"
desc: "Setting up Jest for Next.JS projects"
category_prefix: "Testing: "
indent: true
---


# What is Jest?
Jest was introduced by Facebook for testing Javascript and React applications. It is one of the more popular ways to test React applications.
Jest comes with it's own test runner, you can call Jest from your command line to run all of your tests. 

# Setting Up Jest
To install jest in your Next.JS project, run the following command:
```
npm install --save-dev jest
```
You will also need to create to define a .babelrc file at the top of your app. Which looks like:
```
{
  "presets": ["next/babel"]
}
```
As well as a jest.config.js at the top of your app, which looks like:
```
module.exports = {
  transform: {
    "^.+\\.jsx?$": "babel-jest",
  }
};
```
We also need to add the following script to our package.json
```
"scripts": {
    "test:jest": "jest"
}
```
This allows us to run our entire jest test suite with:
```
npmrun test:jest
```
# Setting up your first Jest Test

Let's start by writing a test for a function that returns the product of two numbers. This function is located in multiply.js.
```
function multiply(a, b) {
  return a * b;
}
module.exports = product;
```

We create a file named multiply.test.js. This will contain the actual jest test.
```
const product = require('./product');

test('multiply 1 * 2 to equal 2', () => {
  expect(multiply(1, 2)).toBe(2);
});
```

Running ``npm run test:jest`` will print the following message:
```
PASS  ./multiply.test.js
✓ multiply 1 * 2 to equal 3 (5ms)
```

This test made use of ``expect`` and ``to be`` to test if two values were identical. Jest has additional matchers that allow us to test exceptions, strings and more.

