<template>
<button :style="{background: color}" class = "btn">{{text}}</button>
  <button>Add Task</button>
</template>

<script>
  export default {
    name: 'Button',
    props: {
      text: String,
      color: String
    }
  }
</script>