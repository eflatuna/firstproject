<template>
	{{ name }}{{ studentIsPassed === "1" ? " (Passed)" : " (Not Passed)" }}
	<button @click="toggleIsPassed()">Gecti Kaldi Degistir</button>
	<button @click="toggleDetail()">
		Bilgileri {{ isVisible ? "gizle" : "goster" }}
	</button>
	<ul v-if="isVisible">
		<li>Age:{{ age }}</li>
		<li>Email:{{ mail }}</li>
	</ul>
</template>

<script>
export default {
	name: "StudentItem",
	// props: ["name", "age", "mail", "isPassed"],
	props: {
		name: {
			type: String,
			required: true,
		},
		age: {
			type: Number,
			required: true,
		},
		mail: {
			type: String,
			required: true,
		},
		isPassed: {
			type: String,
			required: true,
			default: "0",
			validator: function (value) {
				return value === "1" || value === "0";
			},
		},
	},

	data() {
		return {
			isVisible: false,
			studentIsPassed: this.isPassed,
		};
	},
	methods: {
		toggleDetail() {
			this.isVisible = !this.isVisible;
		},
		toggleIsPassed() {
			if (this.studentIsPassed === 1) {
				this.studentIsPassed = 0;
			} else {
				this.studentIsPassed = 1;
			}
		},
	},
};
</script>
