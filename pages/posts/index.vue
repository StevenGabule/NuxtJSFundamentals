<template>
	<div class="container">
		<h2>Making API request - the Vue Way</h2>
		<div class="row">
			<Card v-for="post in posts" :key="post.id" :post="post" class="ml-auto mr-auto" />
		</div>
	</div>
</template>

<script> 
	import axios from 'axios';
	import Card from '@/components/Card';
	export default {
		components: {
			Card
		},
		data() {
			return {
				posts: [],
			}
		},

		async asyncData() {
			let {data} = await axios.get('https://jsonplaceholder.typicode.com/posts');
			return { posts: data}
		},

		head: {
			title: 'List of posts'
		}
	}
</script>