<template>
  	<div>
  		<div class="card my-3" v-for="todo in todos" :key="todo.id">
  			<div class="card-title">
  				<h4 v-show="!edit">{{ todo.title }}</h4>
  				<input type="text" v-show="edit" v-model="todo.title">
  			</div>
  			<hr>
  			<div class="card-body">
  				<p v-show="!edit">{{ todo.body }}</p>
  				<input type="text" v-show="edit" v-model="todo.body">
  			</div>
  			<button class="btn btn-warning my-3" @click.self="editMode">Edit Todo</button>
  			<button class="btn btn-danger" @click= "$emit('del-todo', todo.id)">Delete Todo</button>
  		</div>
  	</div>
</template>
<script>
   	export default {
   		props: ['todos'],
   		data() {
   			return {
   				edit: false
   			}
   		},
   		methods: {
   			editMode() {
   				this.edit = true
   			}
   		}
   	}
</script>
<style>
   
</style>