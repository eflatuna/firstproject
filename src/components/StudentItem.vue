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
	props: ["name", "age", "mail", "isPassed"],
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
