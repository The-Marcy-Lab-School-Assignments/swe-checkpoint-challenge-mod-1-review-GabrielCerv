# Short Responses

For this assessment, aim to write a response with the following qualities:
- [ ] Addresses all parts of the prompt
- [ ] Accurately uses relevant technical terminology
- [ ] Is free of grammar and spelling mistakes
- [ ] Is easy to comprehend

For each prompt below, write your response in the space provided. Aim to answer each prompt in 2-5 concise sentences. Make sure to preview your markdown to check how it is rendered before submitting.

## Prompt 1

Consider the code below which has a bug. Instead of printing the correct letter grade, it always prints `"Your grade is: undefined"`.

```js
const getLetterGrade = (score) => {
  let letter;
  if (score >= 90) {
    let letter = "A";
  } else if (score >= 80) {
    let letter = "B";
  } else if (score >= 70) {
    let letter = "C";
  } else {
    let letter = "F";
  }

  return "Your grade is: " + letter;
}

console.log(getLetterGrade(95)); // This should print "Your grade is: A"
console.log(getLetterGrade(82)); // This should print "Your grade is: B"
console.log(getLetterGrade(74)); // This should print "Your grade is: C"
console.log(getLetterGrade(65)); // This should print "Your grade is: F"
```

**Part A**: Explain why this bug is occurring. Use proper technical terminology.

The bug occurring in this code example is the variable letter is invoked using let. But the issue is that variable letter isn't set to a const variable and is reassigned every time letter is called in the if/ else if statements making it never be assigned a true assigned value so it will always run as undefined.

**Part B**: Then, explain how you would fix it.
 
 I would fix this code by altering the const

### Response 1

**Part A:**

Your response...

The bug occurring in this code example is the variable letter is invoked using let to reassign block scopes. But the issue is that variable letter is reassigned every time letter is called in the if/ else if statements making it never be assigned a true assigned value so it will always run as undefined.

**Part B:**

Your response...

I would remove let from all of the if / else if statements so that the code can update the values of letter without shadowing over each other.

---

## Prompt 2

Read the following code:

```js
const originalSettings = { volume: 50, brightness: 80 };
const newSettings = originalSettings;
newSettings.volume = 75;
console.log(originalSettings.volume);
```

**Part A:** What will be logged to the console? Why does this happen? Be sure to use precise technical terminology in your answer.

**Part B:** How would you modify the code so that changing `newSettings.volume` does NOT affect `originalSettings.volume`? Write the corrected code below your explanation.

### Response 2

**Part A:**

Your response...

75 would be logged onto the console because newSettings and originalSettings when set equal to each other share the same object in memory. This means that when newSettings.volume = 75. When you console log "originalSettings.volume" it will reference the object and mutate it.

**Part B:**

Your response...

```js

const originalSettings = { volume: 50, brightness: 80 };
const newSettings = {...originalSettings}; // spread operator helps prevent creating a shallow copy like original code did.
newSettings.volume = 75;
console.log(originalSettings.volume); 

```
**Corrected Code:**

```js
// Fix this code so newSettings is a true copy
const originalSettings = { volume: 50, brightness: 80 };
const newSettings = originalSettings;
newSettings.volume = 75;
console.log(originalSettings.volume);
```

---

## Prompt 3

Given this array of products and the code using `filter`:
```js
const products = [
  { name: "Laptop", price: 1000, inStock: true },
  { name: "Phone", price: 700, inStock: false },
  { name: "Watch", price: 300, inStock: true },
  { name: "Tablet", price: 500, inStock: true },
];

const itemsInStock = products.filter((product) => {
  return product.inStock
});
```

Walk through what happens in the first iteration of filter:
- What is the value of `product`?
- What gets returned from the callback?
- What happens with that returned value?

### Response 3

Your response...

In the First Iteration of filter:

- The value of `product` is going to be the first object/ product that is stored inside of the products array which is 

```js 

{ name: "Laptop", price: 1000, inStock: true } 

```

In the First Iteration of filter:

- `True` is returned in the callback function because it starts with the 0 index value in the object which is "Laptop" 
isStock is the key value paired to the value `True`


- filter uses the key values: values stored in inStock, and if boolean is true, the value will be kept, and added into the new array itemsInStock and returned.
