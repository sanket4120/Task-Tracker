<template>
  <button :style="{background:bgColor,color:color}">{{text}}</button>
</template>

<script>
export default {
    name:'Button',
    props:{
        text:String,
        bgColor:{
            type:String,
            default:'green'
        },
        color:{
            type:String,
            default:'white',
        }
    }
}
</script>

<style scoped>
    button{
        border: none;
        outline: none;
        padding: 10px 15px;
        font-size: 1rem;
        font-family: inherit;
        border-radius: 4px;
        display: inline-block;
        cursor: pointer;
    }
</style>