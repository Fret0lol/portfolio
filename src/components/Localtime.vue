<script setup>
import {ref, onMounted, onUnmounted} from "vue";

const clock = ref(null);
let timer = null;

const currentTime = () => {
	const date = new Date();
	let hh = date.getHours();
	let mm = date.getMinutes();

	const session = hh < 12 ? "AM" : "PM";

	hh = hh < 10 ? "0" + hh : hh;
	mm = mm < 10 ? "0" + mm : mm;

	const time = hh + ":" + mm + "\n" + session;

	return time;
};

onMounted(() => {
	clock.value = currentTime();
	timer = setInterval(() => {
		clock.value = currentTime();
	}, 1000);
});

onUnmounted(() => {
	clearInterval(timer);
});
</script>
<template>
	<div id="local-time" class="card">
		<div>
			<p class="title">{{ clock }}</p>
			<p class="subtitle">Rennes</p>
			<p class="subtitle">Brittany</p>
		</div>

		<p class="currentTime">Current local time</p>
	</div>
</template>
<style lang="scss" scoped>
#local-time {
  font-family: "Poppins";
	display: flex;
	flex-direction: column;
	justify-content: space-between;
	.title {
		width: 90%;
		white-space: pre-line;
	}
	.subtitle {
		margin-top: 8px;
		color: #fff;
		font-size: 22px;
		font-style: normal;
		font-weight: 500;
	}
	.currentTime {
		color: #42675a;
		font-size: 12px;
		font-style: normal;
		font-weight: 500;
	}
}
</style>
