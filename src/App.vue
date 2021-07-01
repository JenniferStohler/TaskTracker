<template>
<div class="container">
<Header @toggle-add-task="toggleAddTask" title="Task Tracker" :showAddTask="showAddTask" />
<div v-if="showAddTask">
<AddTask @add-task="addTask" />
</div>
<Tasks @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks="tasks"/>
</div>
</template>

<script>

import Header from '../components/Header'
import Tasks from '../components/Tasks'
import AddTask from '../components/AddTask'
export default {
  name: 'App',
  components: {
   Header,
   Tasks,
   AddTask
  },
  data() {
    return {
      tasks: [],
      showAddTask: false,
    }
  },
  methods: {
    toggleAddTask(){
      this.showAddTask = !this.showAddTask
    },
    addTask(task) {
      this.tasks = [...this.tasks, task]
    },
    deleteTask(id){
      if (confirm('Are you sure?')){
        this.tasks = this.tasks.filter((task) => task.id !== id) 

      }
    },
    toggleReminder(id){
     this.tasks = this.tasks.map((task) => task.id === id ? {...task, reminder: !task.reminder} : task )
    }
   },
  createdTasks() {
    this.tasks = [
      {
      id: 1,
      text: 'Work Meeting',
      day: 'June 27th at 1pm',
      reminder: true,
    },
    {
      id: 2,
      text: 'Workout',
      day: 'June 28th at 12pm',
      reminder: true,
    },
    ]
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
