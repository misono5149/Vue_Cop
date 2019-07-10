<template>
    <div class="container">
        <h2>Todo List</h2>
        <div class="input-group" style="margin-bottom:10px;">
            <input type="text" class="form-control" placeholder="Say Something"
            v-model="name" v-on:keyup.enter="createTodo(name)">
            <span class="input-group-btn">
                <button class="btn btn-default" type="button"
                    @click="createTodo(name)">ADD</button>
            </span>
        </div>
        <ui class="list-group">
            <li v-for="(todo, index) in todos" class="list-group-item">
                {{ todo.name }}
            <div class="btn-group pull-right" style="font-size: 12px; line-height:1;">
                <button type="button" class="btn-link dropdown-toggle" data-toggle="dropdown"
                aria-haspopup="true" aria-expanded="false">
                MORE
                <span class="caret"></span>
                </button>
                <ul class="dropdown-menu">
                    <li><a href="#" @click="deleteTodo(index)">DEL</a></li>
                </ul>
            </div>
            </li>
        </ui>
    </div>
</template>

<script>

export default {
    name: 'TodoPage',
  data(){
      return{
          todos: [
              {
                  name:'청소'
              },
              {
                  name:'출근'
              },
              {
                  name:'야근'
              },
              {
                  name:'밥먹기'
              }
          ]
      }
  },
  methods:{
      deleteTodo(i){
          this.todos.splice(i,1);
      },
      createTodo(e){
          if(e !== null){
              this.todos.push({name:e});
              this.e = null;
          }
      }
  },

}
</script>

<style>

</style>
