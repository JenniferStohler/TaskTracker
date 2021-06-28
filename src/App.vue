<template>
<div class="container">
<Header title="Task Tracker"/>
<Tasks :tasks="tasks"/>
</div>
</template>

<script>

import Header from '../components/Header'
import Tasks from '../components/Tasks'
export default {
  name: 'App',
  components: {
   Header,
   Tasks
  },
  data() {
    return {
      tasks: []
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
