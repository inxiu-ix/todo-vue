<template>
  <li>
    <span v-bind:class='{done: todo.completed}'>
    {{todo.title}}
    </span>
    <span>
      <input type="checkbox" @change="todo.completed = !todo.completed">
      <button @click="$emit('remove-todo', todo.id)">&times;</button>
    </span>
  </li>
</template>


<script>
export default {
  props: ['todo']
}
</script>

<style scoped>
.done {
  text-decoration: line-through;
}

</style>