<template>
  <div class="jobs">
      <div v-for="task in tasks" :key="task.id">
          <Task :task="task" @toggle-reminder="$emit('toggle-reminder',task.id)" @remove-task="$emit('remove-task',task.id)" />
      </div>
  </div>
</template>

<script>
import Task from './Task'

export default {
    name:'Tasks',
    components:{Task},
    props:{
        tasks:Array,
    },
    emits:['toggle-reminder','remove-task']
}
</script>

<style>
</style>