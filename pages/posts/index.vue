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
	import {mapGetters} from 'vuex';

	export default {
		components: {
			Card
		},

		data() {
			return {
				allPosts: '',
			}
		},

		computed: {
			...mapGetters(['posts'])
		},
  
		async asyncData({store}) {
			let {data} = await axios.get('https://jsonplaceholder.typicode.com/posts');
			store.dispatch('setPosts', data)
		},

		head: {
			title: 'List of posts'
		}
	}
</script>