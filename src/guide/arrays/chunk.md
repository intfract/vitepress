<script setup>
  import Fract from '/@theme/components/Fract.vue'
</script>

<Fract/>

# Chunk

## Chunk Method

### Description
Splits an array into equal-sized chunks. If the array can not be evenly split, the last array will contain a smaller chunk of items. 

### Example

```js
console.log(_.chunk([0, 'text', [], {}], 3))
// [[0, 'text', []], [{}]]
```

### Parameters
- a (Any Type Array)
- n (Number)