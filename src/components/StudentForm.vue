<template>
	<form @submit.prevent="submitForm">
		<div class="form-control">
			<label>Ad</label>
			<input type="text" v-model="enteredName" />
		</div>
		<div class="form-control">
			<label>Age</label>
			<input type="text" v-model="enteredAge" />
		</div>
		<div class="form-control">
			<label>Email</label>
			<input type="email" v-model="enteredEmail" />
		</div>
		<div class="form-control">
			<label>Dersi Gecme Durumu:</label>
			<input type="checkbox" v-model="enteredIsPassed" />
		</div>
		<button type="submit">Ekle</button>
	</form>
</template>

<script>
export default {
	name: "StudentForm",
	emits: ["addStudent"],
	data() {
		return {
			enteredName: "",
			enteredAge: "",
			enteredEmail: "",
			enteredIsPassed: false,
		};
	},
	methods: {
		submitForm() {
			this.$emit("addStudent", {
				name: this.enteredName,
				age: this.enteredAge,
				email: this.enteredEmail,
				isPassed: this.enteredIsPassed,
			});
			this.enteredName = "";
			this.enteredAge = "";
			this.enteredEmail = "";
			this.enteredIsPassed = false;
		},
	},
};
</script>

<style scoped></style>
