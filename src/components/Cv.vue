<script setup>

import Links from "./Links.vue";
import LocalTime from "./Localtime.vue";
import Stock from './Stock.vue'
</script>

<template>
	<div id="cv">
		<main>
			<div id="profile-photo" class="card">
				<div className="img"></div>
			</div>
			<div class="left">
				<div id="presentation" class="card">
					<p className="title">I'M CLÉMENT</p>
					<p>
						Its been since my college's years since I've honed a passion for design and development and it's something I stand by every day, learning that
						creating something out of passion brings an output of great results. Having to work with people for people, sharing their experience and goals fuels
						me into creating and helping others achieve great results.
					</p>
				</div>
				<div class="middle">
					<div id="skills">
						<div className="skills-container">
							<p className="title">SKILLS</p>
							<ul>
								<li>Application Design</li>
								<li>Front Development</li>
								<li>Back Development</li>
								<li>UI/UX</li>
								<li>Adaptability</li>
							</ul>
						</div>
					</div>
					<LocalTime />
				</div>
			</div>
			<div class="right">
				<Links />
				<div id="mission" class="card">
					<p className="title">
						LAST <br />
						MISSIONS
					</p>
					<div className="missions">
						<div className="mission">
							<div>
								<p className="mission_company">OET</p>
								<p className="mission_date">2021 - 2023</p>
							</div>
							<div className="mission_desc">Design and development</div>
						</div>
						<div className="mission">
							<div>
								<p className="mission_company">Syspertec</p>
								<p className="mission_date">2021</p>
							</div>
							<div className="mission_desc">Front development</div>
						</div>
					</div>
				</div>
				<div className="contact">See my works</div>
			</div>
		</main>
		<div class="footer">
			<div id="aka" class="card">
				<p className="title">AKA</p>
				<p>
					Within the development's community, I'm recognized by the alias
					<span> Fret0lol</span>, a nickname I've been used since the beginning.
				</p>
			</div>
			<Stock />
		</div>
	</div>
</template>

<style scoped lang="scss">
.card {
	padding: 16px 20px;
	border-radius: 16px;
	border: 1px solid rgba(80, 100, 119, 0.5);
}
#cv {
  height: 100%;
  width: 100%;
	max-width: 1440px;
	max-height: 900px;
	display: grid;
	gap: 16px;
	padding: 50px 60px;
}
main {
	width: 100%;
	display: grid;
	grid-template-columns: repeat(9, 1fr) 264px;
	gap: 16px;
	#profile-photo {
		grid-column: 1 / 4;
		.img {
			height: 100%;
			width: 100%;
			background-image: url("../assets/profil-picture.jpg");
			background-position: center;
			background-size: cover;
			border-radius: 12px;
			filter: grayscale(100%);
		}
	}
	.left {
		grid-column: 4 / 10;
		display: grid;
		grid-template-rows: 1fr 1fr;
		gap: 16px;
		#presentation {
			display: flex;
			flex-direction: column;
			justify-content: space-between;
		}
    .middle {
			display: grid;
			grid-template-columns: 2fr 1fr;
			gap: 16px;
      #skills {
				box-sizing: border-box;
				border-radius: 16px;
				background: #5fb3a1;
				color: #ffffff;
				display: flex;
				flex-direction: column;
				justify-content: space-between;
				&:hover {
					.skills-container {
						scale: 0.97 0.95;
					}
				}
				.skills-container {
					height: 100%;
					background: #42675a;
					display: flex;
					flex-direction: column;
					justify-content: space-between;
					color: #ffffff;
					border-radius: 16px;
					padding: 16px 20px;
					transition: 0.2s;
					ul {
						color: #fff;
						font-family: "Poppins";
						font-size: 16px;
						font-style: normal;
						font-weight: 700;
						line-height: 30px; /* 200% */
            list-style: none;
					}
				}
			}	
		}
	}
	.right {
		display: flex;
		flex-direction: column;
		gap: 16px;	
		#mission {
			height: 100%;
			display: flex;
			flex-direction: column;
			justify-content: space-between;
			.missions {
				display: flex;
				flex-direction: column;
				gap: 8px;
				font-family: "Poppins";
				.mission div {
					display: flex;
					justify-content: space-between;
					.mission_company {
						font-size: 16px;
						font-weight: 700;
					}
					.mission_date,
					.mission_desc {
						font-size: 12px;
						font-weight: 400;
					}
				}
			}
		}
		.contact {
			display: flex;
			justify-content: center;
			align-items: center;
			padding: 16px;
			border-radius: 16px;
			border: 1px solid #ffffff;
			background-color: #ffffff;
			color: #5fb3a1;
			font-family: "Poppins";
			font-weight: 700;
		}
	}
}
.footer {
	display: grid;
	grid-template-columns: repeat(12, 1fr);
	gap: 16px;
	#aka {
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		grid-column: 1/4;
	}
}
</style>
