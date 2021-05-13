<template>
  <form @submit.prevent="handleSubmit">
      <div class="form-control">
        <label for="title" >Task</label>
        <input type="text" id="title" placeholder="Enter task" name='title' v-model="title">
      </div>
      <div class="form-control">
        <label for="day" >Day</label>
        <input type="text" id="day" placeholder="Enter day and time" name="day" v-model="day">
      </div>
      <div class="form-checkbox">
        <label for="reminder" >Want to set reminder?</label>
        <input type="checkbox" v-model="reminder" name="reminder">
      </div>
      <Button text="Add Task" bgColor="green" color="white" />
  </form>
</template>

<script>
import Button from './Button'

export default {
    name:'AddTask',
    components:{Button},
    props:{
      addTask:Function
    },
    data(){
      return{
        title:'',
        day:'',
        reminder:false
      }
    },
    methods:{
      handleSubmit(){
        const newTask = {
          id: Math.floor(Math.random() * 1000),
          title:this.title,
          day:this.day,
          reminder:this.reminder
        }
        this.title = ""
        this.day = ""
        this.reminder = false
        this.addTask(newTask)
      }
    }
}
</script>

<style scoped>
    .form-control{
        margin:10px 0;  
    }
    .form-control label{
        display:block;
        margin-bottom:5px;
    }
    .form-control input{
        width: 100%;
        height: 40px;
        padding: 3px 7px;
        font-size: 1rem;
        border: 1px gray solid;
    }
    .form-checkbox{
      display: flex;
      justify-content: space-between;
      align-items: center;
      height:40px;
    }
</style>