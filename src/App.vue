<template>
	<h2>Students</h2>
	<StudentItem
		v-for="student in students"
		:key="student.id"
		:name="student.name"
		:age="student.age"
		:mail="student.email"
		:isPassed="student.isPassed"
		:id="student.id"
		@toggleStudentIsPassed="toggleStudentStatus"
	/>
</template>

<script>
import StudentItem from "./components/StudentItem.vue";

export default {
	name: "App",
	components: { StudentItem },
	data() {
		return {
			students: [
				{
					id: "1",
					name: "Alice",
					age: 20,
					email: "q1w2e@example.com",
					isPassed: true,
				},
				{
					id: "2",
					name: "Bob",
					age: 22,
					email: "q1w2e@example.com",
					isPassed: true,
				},
				{
					id: "3",
					name: "Bob",
					age: 22,
					email: "q1w2e@example.com",
					isPassed: true,
				},
				{
					id: "4",
					name: "Charlie",
					age: 23,
					email: "q1w2e@example.com",
					isPassed: false,
				},
				{
					id: "5",
					name: "David",
					age: 21,
					email: "q1w2e@example.com",
					isPassed: false,
				},
				{
					id: "6",
					name: "Eve",
					age: 22,
					email: "q1w2e@example.com",
					isPassed: false,
				},
			],
		};
	},
	methods: {
		toggleStudentStatus(studentId) {
			console.log(studentId);
			const myStudent = this.students.find(
				(student) => student.id === studentId
			);
			myStudent.isPassed = !myStudent.isPassed;
		},
	},
};
</script>
