<template>
	<h2>Students</h2>
	<StudentItem :data="students" name="can" />
</template>

<script>
import StudentItem from "./components/StudentItem.vue";

export default {
	name: "App",
	components: { StudentItem },
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
