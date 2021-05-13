<template>
  <div class="container">
    <Header :title="title" :toggleAddTask="toggleAddTask" :showAddTask="showAddTask" />
    <div v-if="showAddTask">
          <AddTask :addTask="addTask"/>
    </div>
    <Tasks :tasks="tasks" @toggle-reminder="toggleReminder" @remove-task="removeTask" />
  </div>
</template>

<script>
  import Header from './components/Header'
  import Tasks from './components/Tasks'
  import AddTask from './components/AddTask'

  export default{
    components:{Header, Tasks, AddTask},
    data(){
      return{
        title:'Task Tracker',
        showAddTask:false,
        tasks:[]
      }
    },
    methods:{
      toggleReminder(id){
        this.tasks = this.tasks.map(task => task.id === id ? {...task,reminder:!task.reminder}:task)
      },
      removeTask(id){
        this.tasks = this.tasks.filter(task => task.id !== id)
      },
      addTask(newTask){
        this.tasks = [newTask,...this.tasks]
      },
      toggleAddTask(){
        this.showAddTask = !this.showAddTask;
      }
    }
  }

</script>

<style>
*{
  box-sizing: border-box;
  font-family: montserrat, sans-serif;
  font-weight:300;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.container{
  width: 95%;
  max-width: 500px;
  border: 2px gray solid;
  border-radius: 4px;
  margin: 20px auto;
  padding: 8px;
}

</style>
