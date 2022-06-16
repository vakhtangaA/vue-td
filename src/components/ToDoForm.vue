<template>
  <form @submit.prevent="onSubmit">
    <label for="new-todo-input">
      What needs to be done?
    </label>
    <input
        type="text"
        id="new-todo-input"
        name="new-todo"
        autocomplete="off"
        :value="newTodo"
        required
        v-on:change="newTodo = $event.target.value"
    />
    <button type="submit">
      Add
    </button>
  </form>
</template>

<script>
export default {
  props: {
    addItem: {
      type: Function,
      required: true
    }
  },
  methods: {
    onSubmit(){
      this.$emit('todo-added', this.newTodo);
    }
  },
  data() {
    return {
      newTodo: '',
    }
  },
}

</script>

<style scoped>

</style>