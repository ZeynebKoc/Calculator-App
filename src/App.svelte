<script>
	let display = '';
</script>

<main>
	<div class='header'>
		<h1>calc</h1>
		<div class='nav'>
			<h2>THEME</h2>
			<div class='change-theme'>
				<p class='theme-1'>1</p>
				<p class='theme-2'>2</p>
				<p class='theme-3'>3</p>
				<div class='theme-box'>
					<div class='theme-circle'></div>
				</div>
			</div>
		</div>
	</div>

	<div class='display'>
		<input type='display' bind:value={display} >
		<p></p>
	</div>

	<div class='keypad'>
		<div class='container'>
			<button class='btn'><p>7</p></button>
			<button class='btn'><p>8</p></button>
			<button class='btn'><p>9</p></button>
			<button class='del'><p>DEL</p></button>
			<button class='btn'><p>4</p></button>
			<button class='btn'><p>5</p></button>
			<button class='btn'><p>6</p></button>
			<button class='btn'><p>+</p></button>
			<button class='btn'><p>1</p></button>
			<button class='btn'><p>2</p></button>
			<button class='btn'><p>3</p></button>
			<button class='btn'><p>-</p></button>
			<button class='btn'><p>.</p></button>
			<button class='btn'><p>0</p></button>
			<button class='btn'><p>/</p></button>
			<button class='btn'><p>*</p></button>
			<button class='reset'><p>RESET</p></button>
			<button class='equal'><p>=</p></button>
		</div>
	</div>
</main>

<style>
	main {
		width: 1440px;
		height: 900px;
		background: #3A4663;
	}
	.header {
		position: relative;
		display: flex;
		flex-direction: row;
		width: 540px;
		height: 44px;
		left: 450px;
		top: 96px;
	}
	h1 {
		height: 36px;
		width: 67px;
		left: 0px;
		top: 8px;

		font-family: 'Spartan', sans-serif;
		font-style: normal;
		font-weight: bold;
		font-size: 32px;
		line-height: 36px;
		text-align: center;
		letter-spacing: -0.533333px;
		color: #FFFFFF;
	}
	.nav {
		position: relative;
		display: flex;
		flex-direction: row;
		height: 44px;
		width: 144px;
		left: 396px;
		top: 0px;
	}
	h2 {
		position: relative;
		height: 13px;
		width: 51px;
		left: -80px;
		top: 24px;

		font-family: 'Spartan', sans-serif;
		font-style: normal;
		font-weight: bold;
		font-size: 12px;
		line-height: 13px;
		text-align: center;
		letter-spacing: 1px;
		color: #FFFFFF;
	}
	.change-theme {
		position: relative;
		display: flex;
		flex-direction: row;
		height: 44px;
		width: 71px;
		left: -52px;
		top: 0px;
	}
	.theme-box {
		position: absolute;
		height: 26px;
		width: 71px;
		left: 0px;
		top: 26px;
		border-radius: 13px;
		background: #242D44;
		border-radius: 13px;
	}
	.theme-circle {
		position: relative;
		height: 16px;
		width: 16px;
		left: 5px;
		top: 5px;
		border-radius: 10px;
		background: #D03F2F;
		cursor: pointer;
	}
	.theme-circle:hover {
		background: #F96B5B;
	}
	.theme-1 {
		position: relative;
		height: 13px;
		width: 12px;
		left: 7px;
		top: 0px;

		font-family: 'Spartan', sans-serif;
		font-style: normal;
		font-weight: bold;
		font-size: 12px;
		line-height: 13px;
		text-align: center;
		color: #FFFFFF;
	}
	.theme-2 {
		position: relative;
		height: 13px;
		width: 12px;
		left: 17px;
		top: 0px;

		font-family: 'Spartan', sans-serif;
		font-style: normal;
		font-weight: bold;
		font-size: 12px;
		line-height: 13px;
		text-align: center;
		color: #FFFFFF;
	}
	.theme-3 {
		position: relative;
		height: 13px;
		width: 12px;
		left: 29px;
		top: 0px;

		font-family: 'Spartan', sans-serif;
		font-style: normal;
		font-weight: bold;
		font-size: 12px;
		line-height: 13px;
		text-align: center;
		color: #FFFFFF;
	}
	.display {
		position: absolute;
		width: 540px;
		height: 128px;
		left: 450px;
		top: 172px;
		background: #181F33;
		border-radius: 10px;
	}
	input {
		width: 540px;
		height: 128px;
		left: 450px;
		top: 172px;
		background: #181F33;
		border-radius: 10px;
	}
	input p {
		position: absolute;
		height: 54px;
		width: 201px;
		left: 307px;
		top: 38px;

		font-family: Spartan;
		font-style: normal;
		font-weight: bold;
		font-size: 48px;
		line-height: 54px;

		text-align: right;
		letter-spacing: -0.8px;
		color: #FFFFFF;
	}
	.keypad {
		position: absolute;
		width: 540px;
		height: 480px;
		left: 450px;
		top: 324px;
		background: #242D44;
		border-radius: 10px;
	}
	.container {
		position: relative;
		display: grid;
        grid-template-columns: repeat(4, 101px);
        grid-template-rows: repeat(5, 64px);
		grid-gap: 25px 25px;
		left: 32px;
		top: 32px;
	}
	.reset {
		grid-column-start: 1;
		grid-column-end: 3;
		grid-column: 1 / 3;

		background: #647198;
		box-shadow: inset 0px -4px 0px #414E73;
		border-radius: 10px;
		cursor: pointer;
	}
	.reset:hover {
		background: #A2B2E1;
		box-shadow: inset 0px -4px 0px #414E73;
		border-radius: 10px;
	}
	.reset p {
		position: relative;
		height: 40px;
		width: 166px;
		left: 75px;
		top: -10px;
		
		font-family: 'Spartan', sans-serif;
		font-style: normal;
		font-weight: bold;
		font-size: 20px;
		line-height: 22px;
		display: flex;
		align-items: center;
		text-align: center;
		letter-spacing: -0.333333px;
		color: #FFFFFF;
	}
	.equal {
		grid-column-start: 3;
		grid-column-end: 5;
		grid-column: 3 / 5;

		background: #D03F2F;
		box-shadow: inset 0px -4px 0px #93261A;
		border-radius: 10px;
		cursor: pointer;
	}
	.equal:hover {
		background: #F96B5B;
		box-shadow: inset 0px -4px 0px #93261A;
		border-radius: 10px;
	}
	.equal p {
		position: relative;
		height: 40px;
		width: 166px;
		left: 100px;
		top: -10px;
		
		font-family: 'Spartan', sans-serif;
		font-style: normal;
		font-weight: bold;
		font-size: 20px;
		line-height: 22px;
		display: flex;
		align-items: center;
		text-align: center;
		letter-spacing: -0.333333px;
		color: #FFFFFF;
	}
	.btn {
		background: #EAE3DC;
		box-shadow: inset 0px -4px 0px #B3A497;
		border-radius: 10px;
		cursor: pointer;
	}
	.btn:hover {
		background: #FFFFFE;
		box-shadow: inset 0px -4px 0px #B3A497;
		border-radius: 10px;
	}
	.btn p {
		position: relative;
		height: 40px;
		width: 74px;
		left: 35px;
		top: -20px;
		
		height: 40px;
		font-family: 'Spartan', sans-serif;
		font-style: normal;
		font-weight: bold;
		font-size: 32px;
		line-height: 36px;
		display: flex;
		align-items: center;
		text-align: center;
		letter-spacing: -0.533333px;
		color: #434A59;
	}
	.del {
		background: #647198;
		box-shadow: inset 0px -4px 0px #414E73;
		border-radius: 10px;
		cursor: pointer;
	}
	.del:hover {
		background: #A2B2E1;
		box-shadow: inset 0px -4px 0px #414E73;
		border-radius: 10px;
	}
	.del p {
		position: relative;
		height: 40px;
		width: 74px;
		left: 25px;
		top: -10px;
		
		font-family: 'Spartan', sans-serif;
		font-style: normal;
		font-weight: bold;
		font-size: 20px;
		line-height: 22px;
		display: flex;
		align-items: center;
		text-align: center;
		letter-spacing: -0.333333px;
		color: #FFFFFF;
	}
</style>