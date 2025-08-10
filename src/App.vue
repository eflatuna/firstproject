<template>
	<StudentForm @addStudent="addNewStudent" />
	<div class="main-container">
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
	</div>
</template>

<script>
import StudentItem from "./components/StudentItem.vue";
import StudentForm from "./components/StudentForm.vue";

export default {
	name: "App",
	components: { StudentItem, StudentForm },
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
		addNewStudent(payload) {
			const newStudent = {
				id: new Date().toISOString(),
				name: payload.name,
				age: payload.age,
				email: payload.email,
				isPassed: payload.isPassed,
			};
			this.students.push(newStudent);
		},
	},
};
</script>

<style>
* {
	box-sizing: border-box;
	margin: 0;
	padding: 0;
}

form {
	box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
	max-width: 600px;
	width: 100%;
	margin: 20px auto;
	border-radius: 20px;
	text-align: center;
	padding: 15px;
}

form input {
	width: 100%;
	padding: 5px;
	border-radius: 20px;
}

.form-control {
	margin: 20px;
}

form label {
	font-weight: bold;
	font-size: 20px;
}

.main-container {
	box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
	max-width: 600px;
	width: 100%;
	margin: 20px 0px;
	border-radius: 20px;
	text-align: center;
}
button {
	background-color: green;
	color: white;
	border: none;
	padding: 10px;
	border-radius: 20px;
	cursor: pointer;
	margin: 0px 20px;
}

.student {
	margin: 20px;
}

ul {
	list-style: none;
}

ul li p {
	margin: 5px 0;
	font-weight: bold;
	font-size: 20px;
}
</style>
