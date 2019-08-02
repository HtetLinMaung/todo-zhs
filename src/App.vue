<template>
  <div id="app">

    <app-nav :btnTodo="btnTodo" @btnTodos="btnTodo = $event"></app-nav>

    <div class="col-md-8 offset-md-2 my-3">
      <app-add-todo v-if="btnTodo" @newTodo="addTodo"></app-add-todo>
    </div>
    

    <div class="col-md-8 offset-md-2">
      <app-post :todos="todos" @del-todo="delTodo"></app-post>
    </div>
    
    
  </div>
</template>

<script>

  import Nav from "./components/Navbar.vue"
  import Post from "./components/Post.vue"
  import AddTodo from "./components/AddTodo.vue"

    export default {
          components: {
            appNav: Nav,
            appPost: Post,
            appAddTodo: AddTodo
          },

          data() {
            return {
              btnTodo: false,
              todos: [
                {
                  id: '1',
                  title: 'Something',
                  body: 'Blah Blah Blah'
                },
                {
                  id: '2',
                  title: 'Something 2',
                  body: 'Blah Blah Blah'
                }
              ]
            }
          },

          methods: {
            addTodo (todo) {
              this.todos = [...this.todos, todo];
            },

            delTodo(id) {
              this.todos = this.todos.filter(todo => todo.id !== id)
            }
          }

    }
</script>

<style>


</style>