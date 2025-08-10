<template>
	<div class="student">
		{{ name }}{{ isPassed ? " (Passed)" : " (Not Passed)" }}
		<button @click="toggleIsPassed()">Gecti Kaldi Degistir</button>
		<button @click="toggleDetail()">
			Bilgileri {{ isVisible ? "gizle" : "goster" }}
		</button>
		<ul v-if="isVisible">
			<li>
				<p>Age:</p>
				{{ age }}
			</li>
			<li>
				<p>Email:</p>
				{{ mail }}
			</li>
		</ul>
	</div>
</template>

<script>
export default {
	name: "StudentItem",
	emits: ["toggleStudentIsPassed"],
	// props: ["name", "age", "mail", "isPassed"],
	props: {
		id: {
			type: String,
			required: true,
		},
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
			type: Boolean,
			required: true,
			default: false,
		},
	},

	data() {
		return {
			isVisible: false,
			// studentIsPassed: this.isPassed,
		};
	},
	methods: {
		toggleDetail() {
			this.isVisible = !this.isVisible;
		},
		toggleIsPassed() {
			// this.studentIsPassed = !this.studentIsPassed;
			this.$emit("toggleStudentIsPassed", this.id);
		},
	},
};
</script>
