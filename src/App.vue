<template>
	<h2>Students</h2>
	<ul v-for="student in students" :key="student.name">
		<li>{{ student.name }}</li>
	</ul>
</template>

<script>
export default {
	name: "App",
	data() {
		return {
			students: [
				{ name: "Alice", age: 20 },
				{ name: "Bob", age: 22 },
				{ name: "Charlie", age: 23 },
				{ name: "David", age: 21 },
				{ name: "Eve", age: 22 },
			],
		};
	},
};
</script>
