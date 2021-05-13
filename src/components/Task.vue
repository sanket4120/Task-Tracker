<template>
  <div :class="[task.reminder ? 'reminder':'','task']" @dblclick="$emit('toggle-reminder')">
      <h3>
          {{task.title}}
          <i class="fas fa-times" @click="$emit('remove-task')"></i>
      </h3>
      <p>{{task.day}}</p>
  </div>
</template>

<script>

export default {
    name:'Task',
    props:{
        task:Object
    }
}
</script>

<style>
    .task{
        border: 2px gray solid;
        border-radius: 4px;
        margin: 10px 0;
        padding: 10px;
    }
    .task h3{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    .task h3 i{
        color:red;
        cursor: pointer;
    }
    .reminder{
        border-left: 5px green solid;
    }
    .task h3, .task p{
        margin: 10px;
    }
</style>