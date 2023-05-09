<template>
	<div
		:class="theme === 'light' ? 'light-theme' : 'dark-theme'"
		class="main-body"
	>
		<nav>
			<a href="#" class="logo"><h1>NextCode</h1></a>
			<div style="display: flex; align-items: center; gap: 25px">
				<div class="nav-left">
					<ul>
						<a href="" class="kurs"> nextCode {{ kurs }}</a>
					</ul>
					<div
						style="display: flex; gap: 10px; align-items: center"
						class="pointer"
					>
						<p>{{ til1 }}</p>
						<button @click="till" class="till">
							{{ til }}
						</button>
						<div v-if="tillar" class="tillar">
							<button @click="oz">o'z</button>
							<button @click="rus">pус</button>
							<button @click="ing">ing</button>
						</div>
					</div>
				</div>
				<button
					@click="changeTheme"
					style="display: flex; align-items: center; gap: 5px"
				>
					{{ mavzu }}
					<svg
						xmlns="http://www.w3.org/2000/svg"
						width="16"
						height="16"
						fill="currentColor"
						class="bi bi-palette"
						viewBox="0 0 16 16"
					>
						<path
							d="M8 5a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3zm4 3a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3zM5.5 7a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0zm.5 6a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3z"
						/>
						<path
							d="M16 8c0 3.15-1.866 2.585-3.567 2.07C11.42 9.763 10.465 9.473 10 10c-.603.683-.475 1.819-.351 2.92C9.826 14.495 9.996 16 8 16a8 8 0 1 1 8-8zm-8 7c.611 0 .654-.171.655-.176.078-.146.124-.464.07-1.119-.014-.168-.037-.37-.061-.591-.052-.464-.112-1.005-.118-1.462-.01-.707.083-1.61.704-2.314.369-.417.845-.578 1.272-.618.404-.038.812.026 1.16.104.343.077.702.186 1.025.284l.028.008c.346.105.658.199.953.266.653.148.904.083.991.024C14.717 9.38 15 9.161 15 8a7 7 0 1 0-7 7z"
						/>
					</svg>
				</button>

				<button @click="menuOpen" class="menuOpen">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						width="20"
						height="20"
						fill="currentColor"
						class="bi bi-list"
						viewBox="0 0 16 16"
					>
						<path
							fill-rule="evenodd"
							d="M2.5 12a.5.5 0 0 1 .5-.5h10a.5.5 0 0 1 0 1H3a.5.5 0 0 1-.5-.5zm0-4a.5.5 0 0 1 .5-.5h10a.5.5 0 0 1 0 1H3a.5.5 0 0 1-.5-.5zm0-4a.5.5 0 0 1 .5-.5h10a.5.5 0 0 1 0 1H3a.5.5 0 0 1-.5-.5z"
						/>
					</svg>
				</button>

				<div class="menu-bar" v-if="menuBar">
					<div
						style="
							display: flex;
							justify-content: start;
							width: 100%;
							padding: 10px;
						"
					>
						<button @click="close" style="color: #000">
							<svg
								xmlns="http://www.w3.org/2000/svg"
								width="20"
								height="20"
								fill="currentColor"
								class="bi bi-x-lg"
								viewBox="0 0 16 16"
							>
								<path
									d="M2.146 2.854a.5.5 0 1 1 .708-.708L8 7.293l5.146-5.147a.5.5 0 0 1 .708.708L8.707 8l5.147 5.146a.5.5 0 0 1-.708.708L8 8.707l-5.146 5.147a.5.5 0 0 1-.708-.708L7.293 8 2.146 2.854Z"
								/>
							</svg>
						</button>
					</div>
					<ul>
						<a href="" class="kurs"> nextCode {{ kurs }}</a>
					</ul>
					<div
						style="display: flex; gap: 10px; align-items: center"
						class="pointer"
					>
						<p>{{ til1 }}</p>
						<button @click="till" class="till">
							{{ til }}
						</button>
						<div v-if="tillar" class="tillar">
							<button @click="oz">o'z</button>
							<button @click="rus">pус</button>
							<button @click="ing">ing</button>
						</div>
					</div>
				</div>
			</div>
		</nav>
		<div class="portfel">
			<h1>nextCode {{ Portfel }}</h1>
			<div>
				<div class="portfel-card">
					<p>nextCode sayti</p>
					<a href="https://nextcode-in.netlify.app/">
						<img src="./assets/Screenshot_1.png" alt="next code " />
					</a>
				</div>
				<div class="portfel-card">
					<p>nextCode {{ maktab }}</p>
					<a href="https://nextcode-school.netlify.app/">
						<img src="./assets/Screenshot_2.png" alt="next code school" />
					</a>
				</div>
				<div class="portfel-card">
					<p>nextCode olcha.uz clone</p>
					<a href="https://islombek-olcha.netlify.app/">
						<img src="./assets/Screenshot_3.png" alt="olcha uz" />
					</a>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
export default {
	data() {
		return {
			til: "o'z",
			tillar: false,
			kurs: "kurs",
			theme: "light",
			til1: "til:",
			mavzu: "mavzu",
			Portfel: "Portfel",
			menuBar: false,
			maktab: "maktab",
		};
	},
	methods: {
		changeTheme() {
			console.log("mening temean");
			this.theme = this.theme === "dark" ? "light" : "dark";
		},
		close() {
			this.menuBar = false;
		},
		till() {
			this.tillar = true;
		},
		rus() {
			this.til = "pус";
			this.tillar = false;
			this.kurs = "курс";
			this.til1 = "язык:";
			this.mavzu = "тема";
			this.Portfel = "Портфолио";
			this.maktab = "школа";
		},
		oz() {
			this.til = "o'z";
			this.tillar = false;
			this.kurs = "kurs";
			this.til1 = "til:";
			this.mavzu = "mavzu";
			this.Portfel = "Portfel";
			this.maktab = "msktab";
		},
		ing() {
			this.til = "ing";
			this.tillar = false;
			this.kurs = "course";
			this.til1 = "language:";
			this.mavzu = "theme";
			this.Portfel = "Portfolio";
			this.maktab = "school";
		},
		menuOpen() {
			this.menuBar = !this.menuBar;
		},
	},
};
</script>

<style>
* {
	box-sizing: border-box;
	margin: 0;
}

a {
	text-decoration: none;
}

.main-body {
	height: 100%;
}
.light-theme {
	background-color: white;
	color: black;
}
.light-theme a {
	color: black;
}
.dark-theme {
	background-color: black;
	color: white;
}
.dark-theme a {
	color: white;
}
.dark-theme .till {
	color: white;
	border-left: 1px solid white;
}
.dark-theme nav {
	box-shadow: 0 0 15px white;
}

.light-theme .menu-bar {
	background: #000;
	color: #fff;
	box-shadow: 0 0 20px #000;
}
.light-theme .menu-bar a {
	color: #fff;
}
.light-theme .menu-bar button {
	color: #fff;
}
.light-theme .menu-bar .till {
	border-left: 1px solid #fff;
}

.dark-theme .menu-bar {
	background: #fff;
	color: #000;
	box-shadow: 0 0 20px #fff;
}
.dark-theme .menu-bar a {
	color: #000;
}
.dark-theme .menu-bar button {
	color: #000;
}
.dark-theme .menu-bar .till {
	border-left: 1px solid #000;
}

.menu-bar {
	position: absolute;
	right: 0;
	top: 0;
	width: 50%;
	height: 100vh;
}

.menu-bar ul {
	margin-bottom: 25px;
}
.menu-bar .tillar {
	top: 130px;
}
.menu-bar .tillar button {
	color: #000;
}
nav {
	width: 100%;
	display: flex;
	justify-content: space-around;
	padding: 15px 0;
	box-shadow: 0 0 15px black;
}
.menu-bar {
	display: flex;
	flex-direction: column;
	align-items: center;
}

.logo {
	font-size: 28px;
	font-style: unset;
}
.nav-left {
	display: flex;
	align-items: center;
	gap: 40px;
}

ul {
	display: flex;
	gap: 50px;
	align-items: center;
}

.kurs {
	font-size: 23px;
}
.pointer button {
	cursor: pointer;
}
.till {
	border: none;
	background-color: transparent;
	border-left: 1px solid black;
}
.tillar {
	position: absolute;
	display: flex;
	flex-direction: column;
	top: 70px;
	padding: 10px 25px;
	border: 1px solid black;
	gap: 7px;
	border-radius: 5px;
	background: dimgrey;
}
.portfel {
	display: flex;
	flex-direction: column;
	align-items: center;
	padding: 25px 0;
}
.portfel-card {
	margin-top: 50px;
}
.portfel-card p {
	margin-bottom: 10px;
	font-size: 17px;
	margin-left: 20px;
}
img {
	width: 700px;
}
.menuOpen {
	display: none;
}
@media (max-width: 720px) {
	img {
		width: 400px;
	}
}
@media (max-width: 587px) {
	img {
		width: 350px;
	}
	.logo {
		font-size: 19px;
	}
	.nav-left {
		display: none;
	}
	.menuOpen {
		display: block;
	}
}
</style>
