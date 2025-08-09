<template>
	<ul v-for="student in data" :key="student.name">
		<li>{{ student.name }}</li>
	</ul>

	{{ name }}
</template>

<script>
export default {
	name: "StudentItem",
	props: [
		"name",
		"data",
		// You can add more props if needed, e.g., age
	],
	data() {
		return {};
	},
};
</script>
