<template>
	<div class="container">
		<div class="row">
			<div class="col">
				<h2>Making API request - the Vue Way</h2>
				<p v-for="post in posts" :key="post.id">{{ post.title }}</p>
			</div>
		</div>
	</div>
</template>

<script>
	import axios from 'axios';
	export default {
		data() {
			return {
				posts: []
			}
		},

		mounted() {
			axios.get('https://jsonplaceholder.typicode.com/todos')
				.then(response => {
					console.log(response)
					this.posts = response.data;
				})
				.catch(error => {
					console.error(error)
				})
				return { posts: response.data}
		}
	}
</script>