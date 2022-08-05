<script setup>
  import Fract from '/@theme/components/Fract.vue'
</script>

<Fract/>

# Filtration

This section contains one of the best functions [Defract](https://npmjs.com/package/defract) has to offer! 
> These methods mainly work with an array of objects

## Filter Method

### Description
Returns an array of objects that meet the key and value requirements. If the callback returns a falsy value, the item is removed from the new array. 

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

console.log(_.filter(users, _.must({ age: '> 16' })))
// [{ name: 'John', age: 18, deleted: false }, { name: 'Bob', age: 69, deleted: true }]
console.log(_.filter(users, { age: 13 })) // _.matches shorthand
// [{ name: 'Jane', age: 13, deleted: false }]
console.log(_.filter(users, ['name', 'John'])) // _.matchesProperty shorthand
// [{ name: 'John', age: 18, deleted: false }]
console.log(_.filter(users, 'deleted')) // _.property shorthand
// [{ name: 'Bob', age: 69, deleted: true }]
```

### Parameters
- a (Object Array)
- rule (Function | Object | Array = 2 | String)

## Find Method

### Description
Returns the first item that meets the key and value requirements. 

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

console.log(_.find(users, _.must({ age: '> 16' })))
// { name: 'John', age: 18, deleted: false }
console.log(_.find(users, { age: 13 })) // _.matches shorthand
// { name: 'Jane', age: 13, deleted: false }
console.log(_.find(users, ['name', 'John'])) // _.matchesProperty shorthand
// { name: 'John', age: 18, deleted: false }
console.log(_.find(users, 'deleted')) // _.property shorthand
// { name: 'Bob', age: 69, deleted: true }
```

### Parameters
- a (Object Array)
- rule (Function | Object | Array = 2 | String)

## Find Indexes Method

### Description
Returns an array containing the indexes of items that meet the key and value requirements. 

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

console.log(_.findIndexes(users, _.must({ age: '> 16' })))
// [0, 2]
console.log(_.findIndexes(users, { age: 13 })) // _.matches shorthand
// [1]
console.log(_.findIndexes(users, ['name', 'John'])) // _.matchesProperty shorthand
// [0]
console.log(_.findIndexes(users, 'deleted')) // _.property shorthand
// [2]
```

### Parameters
- a (Object Array)
- rule (Function | Object | Array = 2 | String)

## Distill Method

### Description
Returns an array with two items. The first item `[0]` contains items that meet the key and value requirements. The second item `[1]` contains items that do not meet the key and value requirements. 

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

/* Comments were made compact */

console.log(_.distill(users, _.must({ age: ['&&', '>= 13', '<= 18'] })))
// [[John, Jane], [Bob]]
console.log(_.distill(users, { age: 13 })) // _.matches shorthand
// [[Jane], [John, Bob]]
console.log(_.distill(users, ['name', 'John'])) // _.matchesProperty shorthand
// [[John], [Jane, Bob]]
console.log(_.distill(users, 'deleted')) // _.property shorthand
// [[Bob], [John, Jane]]
```

### Parameters
- a (Object Array)
- rule (Function | Object | Array = 2 | String)