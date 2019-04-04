<template>
	<div class="root">
		<button class="btn-primary" v-bind:disabled="status" v-on:click="func()">btn2</button>
		<div class="progress">
			<div class="progress-bar" v-bind:style="width"></div>
		</div>
	</div>
</template>

<style></style>

<script>
export default {
	data() {
		return {
			width: "width: 0%",
			step: 10,
			n: 0,
			status: false
		}
	},
	methods: {
		func() {
			if (this.n >= 100) {
				this.status = !this.status;
				return;
			};
			this.n += this.step;
			this.width = `width: ${this.n}%`;
		}
	}
}

</script>
