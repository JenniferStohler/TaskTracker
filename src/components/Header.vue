<template>
  <header>
    <h1>{{ title }}</h1>
    <Button text="Add Task" color="green" />
    <Button text="Edit Task" color="orange" />
    <Button text="Delete Task" color="red" />
</template>
<script>
import Button from '../components/Button'
export default {
  name: 'Header',
  props: {
    title: String
  },
  components: {
    Button
  }
}
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>