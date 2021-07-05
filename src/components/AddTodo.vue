<template>
  <form @submit.prevent="onSubmit">
    <input type="text" v-model="title" />
    <button type="submit">Add todo</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      title: '',
    };
  },
  methods: {
    onSubmit() {
      console.log('submit', this.title)
      if (this.title.trim()) {
        const newTodo = {
          title: this.title,
          id: +new Date(),
          completed: false,
        };
        this.$emit('add-todo', newTodo);
        this.title = '';
      }
    },
  },
};
</script>
