<template>
  <div>
    <input type="checkbox" :id="id" :checked="isDone" />
    <label :for="id">{{label}}</label>
  </div>
</template>

<script>
import uniqueId from 'lodash.uniqueid';

export default {
  props: {
    label: {
      type: String,
      required: true
    },
    done: {
      type: Boolean,
      default: false
    },
  },
  data() {
    return {
      isDone: this.done,
      id: uniqueId('todo-item-')
    }
  },
}
</script>