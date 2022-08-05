<script setup>
  import Fract from '/@theme/components/Fract.vue'
</script>

<Fract/>

# Conditionals

These methods are quite unique to [Defract](https://npmjs.com/package/defract)!

## Countif Method

### Description
Finds the count of items that meet the condition. Works like the `countif` formula in spreadsheets. 

### Example

```js
const users = [
  {
    name: 'John',
    age: 18,
    deleted: false
  },
  {
    name: 'Jane',
    age: 13,
    deleted: false
  },
  {
    name: 'Bob',
    age: 69,
    deleted: true
  },
]

console.log(_.countif(users, '.age > 13'))
// 2
console.log(_.countif(users, ['&&', '.age > 13', '.deleted === false']))
// 1
```

### Parameters
- a (Array)
- rule (String | String Array > 1)

## Ifelse Method

### Description
Returns an array of items with positive and negative indicators. Works like the `if` formula in spreadsheets. 

### Example

```js
const users = [
  {
    name: 'John',
    age: 18,
    deleted: false
  },
  {
    name: 'Jane',
    age: 13,
    deleted: false
  },
  {
    name: 'Bob',
    age: 69,
    deleted: true
  },
]

console.log(_.ifelse(users, 'Yes', 'No', (item) => { return item.age > 13 }))
// ['Yes', 'No', 'Yes']
```

### Parameters
- a (Array)
- rule (Function)