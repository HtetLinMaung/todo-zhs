<template>
	<div>
		<form>
			<div class="form-group bg-success">
				<input type="text" v-model="title" class="form-control">
			</div>

			<div class="form-group">
				<textarea class="form-control" v-model="body"></textarea>
			</div>
			<input type="submit" @click.prevent="addTodo" class="btn btn-sm btn-outline-primary">
		</form>
		
	</div>
</template>

<script>
	import uuid from 'uuid'

	export default {
		data() {
			return {
				title: '',
				body: ''
			}
		},
		methods: {
			addTodo() {
				const newTodo = {
						id: uuid.v4(),
						title: this.title,
						body: this.body
					}
				this.$emit('newTodo',newTodo);
			}
		}
	}
</script>