<template>
	{{ name }}
	<button @click="toggleDetail()">
		Bilgileri{{ isVisible ? "gizle" : "goster" }}
	</button>
	<ul v-if="isVisible">
		<li>Age:{{ age }}</li>
		<li>Email:{{ mail }}</li>
	</ul>
</template>

<script>
export default {
	name: "StudentItem",
	props: ["name", "age", "mail"],
	data() {
		return {
			isVisible: false,
		};
	},
	methods: {
		toggleDetail() {
			this.isVisible = !this.isVisible;
		},
	},
};
</script>
