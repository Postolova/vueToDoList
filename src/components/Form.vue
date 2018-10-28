<template>
  <form @submit.prevent="addTask" ref="formTask">
    <label for="title">Title</label>
    <input v-model="title" id="title" type="text">
    <label for="desc">Desc</label>
    <input v-model="desc" id="desc" type="text">
    <button type="submit">Add task</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      title: '',
      desc: ''
    }
  },
  methods: {
    addTask() {
      this.$emit('onTaskAdd', {
        title: this.title,
        desc: this.desc,
        complete: false
      });
      this.$refs.formTask.reset();
    }
  }
}
</script>



