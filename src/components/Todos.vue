<template>
    <div class="todo-list">
        <link rel="stylesheet" href="https://ez-css.now.sh">
        <h3>{{ title }}</h3>
        <form @submit.prevent="addTodo">
            <label for="newTodo">New Todo</label>
            <input type="text" name="newtodo" id="newTodo" 
            placeholder="New Todo" v-model="newTodo">
            <button type="submit" name="button">add</button>
        </form>
        
        <!-- <button type="button" @click="alldone">All Done</button> -->
        
        <ul>
            <li v-for="todo in todos" :key="todo">
                <input type="checkbox" v-model ="todo.done" id="checkDone">
                <span id="textItem" :class="{done : todo.done}">   {{todo.title}}    </span>
                <button id="removeItem" @click="removeTodo(todo)">apagar</button>
            </li>
        </ul>

    </div>
</template>

<script>
export default {
  name: 'Todos',
  data(){
    return {
        title: 'Todos test app',
        count: 1,
        newTodo: '',
        todos: []
    }
  },
  methods:{
      addTodo(){
          this.todos.push({
              title: this.newTodo,
              done: false
          });
          this.newTodo = '';
      },
      removeTodo(todo){
          const todoIndex = this.todos.indexOf(todo);
          this.todos.splice(todoIndex,1);
      },
      allDone(){
          this.todos.forEach(todo => {
              todo.done = true;
          })
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .done{
        text-decoration: line-through;
    }
    .app{
        background-color: #e5e7ea;
    }
    li{
        font-size: 25px;
    }
    .todo-list{
        width: 50%;
        margin: auto;
    }
    #textItem{
        color: orange;
        width: 65%;
    }
    #checkDone{
        width: 5%;
    }
    #removeItem{
        border-style: hidden;
        border-radius: 20;
        width: 30%;
        text-size-adjust: 12px;
        text-align: center;
        font-weight: bold;
    }
    
</style>
