<template>
    <div class="app">
      <div class="container">
        <div class="row header">
          <h1 class="col center-align teal-text">To Do List</h1>
  
          <form @submit.prevent="submitTodo">
            <div class="input-field">
              <textarea v-model="newTodo" class="materialize-textarea"> </textarea>
            </div>
            <button class="btn-add">Adicionar</button>
          </form>
  
        </div>
        <div class="row">
        </div>
        <div class="row">
          <ul class="collection col">
            <li class="collection-item" v-for="todo in todos" :key="todo.id">
              <p>
                <label>
                  <input type="checkbox" class ="checkbox" :checked=todo.done @change="todo.done = !todo.done" />
                  <span>{{todo.title}}</span>
                  <span>
                    <a @click.prevent="deleteTodo(todo)">
                      <i class="delete-task"> x </i>
                    </a>
                  </span>
                </label>
              </p>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ToDoList',
    data() {
      return {
        todos: [],
        newTodo: '',
      };
    },
    watch: {
      todos: {
        handler() {
          localStorage.todos = JSON.stringify(this.todos);
        },
        deep: true,
      },
    },
    mounted() {
      if (localStorage.todos) {
        this.todos = JSON.parse(localStorage.todos);
      }
    },
    methods: {
      submitTodo() {
        this.todos.push({
          title: this.newTodo,
          done: false,
        });
        this.newTodo = '';
      },
      deleteTodo(todo) {
        const todoIndex = this.todos.indexOf(todo);
        this.todos.splice(todoIndex, 1);
      },
    },
  };
  </script>
  
  <style >
  
  @import "https://unpkg.com/open-props";
  
  h1, li{
    color: #000000;
    margin: 1px;
  }
  textarea{
    width: 20em;
    height: 2.5em;
    padding: 4px;
  }
  span{
    font-size: 1em;
    padding: 5px;
  }
  input[type=checkbox]:before {
    content: "";
    display: block;
    position: absolute;
    width: 16px;
    height: 16px;
    top: 0;
    left: 0;
    border: 2px solid #555555;
    border-radius: 3px;
    background-color: white;
  }
  input[type=checkbox]:checked:after {
   content: "";
   display: block;
   width: 5px;
   height: 10px;
   border: solid black;
    border-width: 0 2px 2px 0;
   -webkit-transform: rotate(45deg);
   -ms-transform: rotate(45deg);
   transform: rotate(45deg);
   position: absolute;
   top: 2px;
   left: 6px;
  }

  .delete-task{
    color: red;
  }

  .btn-add {
    margin: 1em 4.5em;
    padding: 15px 30px;
    background-color: #ffc8e0;
    color: #3a3a3a;
    font-weight: bold;
    border: none;
    border-radius: 5px;
    letter-spacing: 4px;
    overflow: hidden;
    transition: 0.5s;
    cursor: pointer;
  }

  button:hover{
      background: #B4E4FF;
      color: #050801;
      box-shadow: 0 0 5px #B4E4FF;
  }
  </style>