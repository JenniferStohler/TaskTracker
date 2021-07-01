<template>
  <form @submit="onSubmit">
  <div class="form-group">
    <label for="exampleInputTask"></label>
    <input type="text" class="form-control" id="exampleInputTask" v-model="text" name="text" placeholder="Add Task">
    
  </div>
  <div class="form-group">
    <label for="exampleInputDate">Date and Time</label>
    <input type="date" class="form-control" id="exampleInputDate" v-model="date" placeholder="Add Date and Time">
  </div>
  <div class="form-group form-check">
    <input type="checkbox" class="form-check-input" id="exampleCheck1">
    <label class="form-check-label" for="exampleCheck1" placeholder="Set Reminder">Set Reminder</label>
  </div>
  <button type="submit" class="btn btn-primary">Submit</button>
</form>
</template>

<script>
export default {
  name: 'AddTask',
  data() {
    return {
      text: '',
      day: '',
      reminder: false
    }
  },
  methods: {
    onSubmit(e) {
      e.preventDefault()
      if(!this.text) {
        alert('Please add a task')
        return
      }
      const newTask = {
        id: Math.floor(Math.random() * 100000),
        text: this.text,
        day: this.day,
        reminder: this.reminder
      }
    console.log(newTask)
      this.text = ''
      this.day = ''
      this.reminder = ''
    }
  }
}
</script>