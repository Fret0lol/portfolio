<script setup>
import {gsap} from "gsap";
import {onMounted} from "vue";

onMounted(() => {
	gsap.set(".cursor", {xPercent: -50, yPercent: -50});

	let xTo = gsap.quickTo(".cursor", "x", {duration: 0.6, ease: "power3"}),
		yTo = gsap.quickTo(".cursor", "y", {duration: 0.6, ease: "power3"});

	window.addEventListener("mousemove", (e) => {
		xTo(e.clientX);
		yTo(e.clientY);
	});
});
</script>
<template>
	<div class="cursor"></div>
</template>
<style lang="scss" scoped>
.cursor {
	width: 35px;
	height: 35px;
	position: fixed;
	top: 0;
	left: 0;
  background-color: #5fb3a1;
	border-radius: 50%;
	pointer-events: none;
}
</style>
