<script setup>
import {onMounted} from "vue";

let icons = [];

onMounted(() => {
	icons = document.querySelectorAll(".dock-container li");

	icons.forEach((item, index) => {
		item.addEventListener("mouseover", () => {
			focus(item, index);
		});
		item.addEventListener("mouseleave", () => {
			icons.forEach((item) => {
				item.style.transform = "scale(1) translateY(0px)";
			});
		});
	});

	const focus = (elem, index) => {
		const previous = index - 1;
		const previous1 = index - 2;
		const next = index + 1;
		const next1 = index + 2;

		elem.style.transform = "scale(1.5) translateY(-10px)";

		if (previous == -1) {
			icons[next].style.transform = "scale(1.2) translateY(-6px)";
			icons[next1].style.transform = "scale(1.1)";
		} else if (previous == 0) {
			icons[next].style.transform = "scale(1.2) translateY(-6px)";
		} else if (next == icons.length) {
			icons[previous].style.transform = "scale(1.2) translateY(-6px)";
			icons[previous1].style.transform = "scale(1.1)";
		} else if (next == icons.length - 1) {
			icons[previous].style.transform = "scale(1.2) translateY(-6px)";
		} else {
			icons[previous].style.transform = "scale(1.2) translateY(-6px)";
			icons[previous1].style.transform = "scale(1.1)";
			icons[next].style.transform = "scale(1.2) translateY(-6px)";
			icons[next1].style.transform = "scale(1.1)";
		}
	};
});
</script>
<template>
	<div id="stock" class="card">
		<p className="title">STOCK</p>
		<div className="dock-container">
			<ul className="dock">
				<li className="li-1">
					<div className="name">Vue.js</div>
					<img src="../assets/vue.svg" />
				</li>
				<li className="li-2">
					<div className="name">React</div>
					<img src="../assets/react.svg" />
				</li>
				<li className="li-3">
					<div className="name">Figma</div>
					<img src="../assets/figma.svg" />
				</li>
				<li className="li-4">
					<div className="name">Spring</div>
					<img src="../assets/spring.svg" />
				</li>
				<li className="li-5">
					<div className="name">Java</div>
					<img src="../assets/java.svg" />
				</li>
				<li className="li-6">
					<div className="name">Node.js</div>
					<img src="../assets/nodejs.svg" />
				</li>
			</ul>
		</div>
	</div>
</template>
<style lang="scss" scoped>
#stock {
	grid-column: 4/13;
	display: flex;
	flex-direction: column;
	justify-content: space-between;
	.dock-container {
		display: flex;
		justify-content: center;
		align-items: center;
		.dock {
			display: flex;
			justify-content: center;
			width: 500px;
			border-radius: 16px;
			border: 1px solid rgba(255, 255, 255, 0.11);
			gap: 10px;
			padding: 10px 15px;
			li {
				position: relative;
				list-style: none;
				display: flex;
				justify-content: center;
				align-items: center;
				width: 50px;
				height: 50px;
				vertical-align: bottom;
				transition: 0.2s;
				transform-origin: 50% 50%;
				background-color: #ffffff;
				border-radius: 10px;
				&:hover {
					margin: 0px 15px;
					.name {
						opacity: 1;
					}
				}
				.name {
					position: absolute;
					top: -25px;
					background-color: rgba(23, 23, 23, 0.67);
					border: 0.5px solid rgba(255, 255, 255, 0.1);
					color: rgba(255, 255, 255, 0.9);
					height: 20px;
					padding: 1px 5px;
					display: flex;
					align-items: center;
					justify-content: center;
					border-radius: 2px;
					font-family: "Poppins";
					font-size: 10px;
					opacity: 0;
				}
				img {
					width: 80%;
					height: 80%;
					transition: 0.2s;
				}
			}
		}
	}
}
</style>
