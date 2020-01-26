<template>
	<div class="card text-white bg-dark mb-3" style="max-width: 18rem;">
	  <div class="card-header">Post No. {{ post.id }}</div>
	  <div class="card-body">
	    <h5 class="card-title">{{ post.title}}</h5>
	    <nuxt-link :to="{name: 'posts-id', params: { id: post.id }}" class="btn btn-primary">See more</nuxt-link>	
	  </div>
	</div>
</template>

<script>
	export default {
		props: {
			post: Object
		}
	}
</script>