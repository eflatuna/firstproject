<template>
	<h2>Students</h2>
	<StudentItem name="Alice" age="20" mail="q1w2e@example.com" />
	<StudentItem name="Bob" age="22" mail="KlJ5g@example.com" />
	<StudentItem name="Charlie" age="23" mail="q1w2e@example.com" />
	<StudentItem name="David" age="21" mail="q1w2e@example.com" />
	<StudentItem name="Eve" age="22" mail="q1w2e@example.com" />
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
