<template>
	<div>
		<div class="container-fluid p-0">
			<nav class="navbar navbar-expand-lg navbar-light bg-secondary px-5">
			  <a class="navbar-brand" href="#">Home</a>
			  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
			    <span class="navbar-toggler-icon"></span>
			  </button>

			  <div class="collapse navbar-collapse" id="navbarSupportedContent">
			    <ul class="navbar-nav mr-auto">
			      <li class="nav-item active">
			        <a class="nav-link" href="#">Something <span class="sr-only">(current)</span></a>
			      </li>
			    </ul>

			    <button class="btn btn-success mr-2" @click="openTodo">Add New Todo</button>

			    <form class="form-inline my-2 my-lg-0">
			      <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
			      <button class="btn btn-outline-warning my-2 my-sm-0" type="submit">Search</button>
			    </form>
			  </div>
			</nav>
		</div>
	</div>
</template>

<script>
	export default {
		props:['btnTodo'],

		methods: {
			openTodo() {
				this.btnTodo = !this.btnTodo;
				this.$emit('btnTodos', this.btnTodo);
			}
		}
	}
</script>