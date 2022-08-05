<script setup>
  import Fract from '/@theme/components/Fract.vue'
</script>

<Fract/>

# Operations

This section covers the essentials of using logic operators on data. These methods are extremely effective on arrays with unique values. 
> These methods do not guarantee unique values to allow flexibility 

## Unite Method

### Description
Unites multiple arrays together by concatenating them together. 

### Example

```js
console.log(_.unite([0, 'text', [], {}], [0, 'text'], [0, 'text', [], {}]))
// [0, 'text', [], {}, 0, 'text', 0, 'text', [], {}]
console.log(_.unite([0, 'text', [], {}], 'string'))
// [0, 'text', [], {}, 'string']
```

### Parameters
- ...arrays (Arrays)

## Subtract Method

### Description
Subtracts multiple arrays from a target array. 

### Example

```js
console.log(_.subtract([0, 'text', [], {}, [0, 1]], [0, []], [{}]))
// ['text', [0, 1]]
```

### Parameters
- target (Array)
- ...arrays (Arrays)

## Intersect Method

### Description
Returns the common items of multiple arrays. The count of common items is preserved in the new array. 

### Example

```js
console.log(_.intersect([0, 'text', [], {}], [0, 'text'], ['text', {}]))
// ['text', 'text', 'text']
```

### Parameters
- ...arrays (Arrays)

## Exclude Method

### Description
Returns the symmetric difference of multiple arrays. 

### Example

```js
console.log(_.exclude([0, 'text', [], {}], [0, 'text'], ['text', {}]))
// [[]]
```

### Parameters
- ...arrays (Arrays)