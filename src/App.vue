<script >
import { computed, reactive, ref } from 'vue';

export default{
      setup() {
        const newTodo = ref('')
        const todos = ref([])
        function addNewTodo(){
          // console.log(newTodo.value);
          todos.value.push({
            done: false,
            content: newTodo.value
          })
        }
        return {
          todos,
          newTodo,
          addNewTodo,
        };
      }
    }


</script>

<template>
  <h1>Vue 3 Todo App</h1>
   <form @submit.prevent="addNewTodo">
    <label >New Todo</label>
    <input v-model="newTodo" name="newTodo">
    <button>Add New Todo</button>
  </form> 
  <div v-for="todo in todos">
    
    <h3>{{ todo.content }}</h3>

  </div>
  
</template>

<style scoped>


</style>
