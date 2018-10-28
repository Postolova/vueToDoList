<template>
  <div>
    <taskForm @onTaskAdd="addTask"></taskForm>
    <ul>
      <task v-for="(task, index) of tasks" :key="task.title" :task="task"
      @onDeleteTask="deleteTask" @onChecked="checkedTask(index)"></task>
    </ul>
  </div>
</template>

<script>
import taskForm from './components/Form'
import task from './components/Task'
export default {
  data() {
    return {
      tasks: [
        {
          title: 'Task 1',
          desc: 'фывфы фыв фыв фыв фыв фыв фыв',
          complete: false
        },
        {
          title: 'Task 2',
          desc: 'фывфы фыв фыв фыв фыв фыв фывфыв',
          complete: false
        },
        {
          title: 'Task 3',
          desc: 'фывфы фыв фыв фыв фыв фыв фывфывфы',
          complete: false
        },
        {
          title: 'Task 4',
          desc: 'тртрт тр фывфы фыв фыв фыв фыв фыв фывтрт р',
          complete: false
        }
      ]
    }
  },
  methods: {
    addTask(task) {
      this.tasks.push(task);
    },
    deleteTask(task) {
      console.log(task);
      this.tasks.filter(i => i !== task);
    },
    checkedTask(index) {
      this.tasks[index].complete = true;
    }
  },
  components: {
    taskForm,
    task
  },
  // mounted () {
  //   this.getPosts()
  // }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
