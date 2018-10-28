<template>
  <li :class="{ 'done': task.complete }">
    <div>{{ task.title }}</div>
    <p>{{ task.desc }}</p>
    <button type="button" v-on:click="checkTask">Checked</button>
    <button type="button" v-on:click="deleteTask">Delete</button>
  </li>
</template>
<script>
export default {
  props: {
    task: {
      type: Object
    }
  },
  methods: {
    checkTask() {
      this.$emit('onChecked');
    },
    deleteTask() {
      this.$emit('onDeleteTask', this.task);
    }
  }
}
</script>

<style lang="scss">
.done {
  div {
    text-decoration: line-through;
  }
}
</style>
