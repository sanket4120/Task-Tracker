<template>
    <header>
        <h1>{{title}}</h1>
        <Button :text="showAddTask?'Close':'Add Task'" :bgColor="showAddTask?'red':'green'" @click="toggleAddTask" />
    </header>
</template>

<script>
import Button from './Button'
export default{
    name:'Header',
    components:{Button},
    props:{
        title:String,
        toggleAddTask:Function,
        showAddTask:Boolean
    }
}
</script>

<style scoped>
    header{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
</style>