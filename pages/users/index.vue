<template>
	<div>
		<h1>Hello, users</h1>
		<input type="text" v-model="id" placeholder="Enter a valid id" @keyup.13="loadUser">
		<button @click="loadUser">Load User</button>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				id: ''
			}
		},
		methods: {
			loadUser() {
				this.$router.push(`/users/${this.id}`);
			}
		}
	}
</script>