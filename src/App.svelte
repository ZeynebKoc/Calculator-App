<script>
	let display = document.getElementById('display');

	const addDisplay = (num) => {
		display += num;
	} 
	const resetDisplay = () => {
		display = '';
	}
	const deleteNum = () => {
		display = display.slice(0, -1);
	}
	const equal = () => {
		var exp = display;
		if (exp){
			display=eval(display);
		}
		console.log(equal);
	} 
	
	const changeTheme = () => {
		switch(theme) {
			case 'theme1':
				document.getElementById("theme-blue").style;
				break;
			case 'theme2':
				document.getElementById("theme-white").style;
				break;
			case 'theme3':
				document.getElementById("theme-purple").style;
				break;
			default:
				document.getElementById("theme-blue").style;
				break;
		}
	}
	
</script>

<link rel="stylesheet" type="text/css" id='theme-blue' href="./themes/theme1.css" />
<link rel="stylesheet" type="text/css" id='theme-white' href="./themes/theme2.css" />
<link rel="stylesheet" type="text/css" id='theme-purple' href="./themes/theme3.css" />

<main>
	<div class='header'>
		<h1>calc</h1>
		<div class='nav'>
			<h2>THEME</h2>
			<div class='change-theme'>
				<p class='theme-1'>1</p>
				<p class='theme-2'>2</p>
				<p class='theme-3'>3</p>
				<input type=range class="range" min=1 max=3 step="1" list="theme-range"/>
				<datalist id="theme-range">
					<option value='1' id="theme-blue" on:click={()=>changeTheme}></option>
					<option value='2' id="theme-white" on:click={()=>changeTheme}></option>
					<option value='3' id="theme-purple" on:click={()=>changeTheme}></option>
				</datalist>
			</div>
		</div>
	</div>
	<div class='display' >
		<input type='text' bind:value={display}/>
	</div>
	<div class='keypad'>
		<div class='container'>
			<button class='btn' value='7' on:click={()=>{addDisplay(7)}}><p>7</p></button>
			<button class='btn' value='8'on:click={()=>{addDisplay(8)}}><p>8</p></button>
			<button class='btn' value='9' on:click={()=>{addDisplay(9)}}><p>9</p></button>
			<button class='del' value='DEL' on:click={()=>{deleteNum()}}><p>DEL</p></button>
			<button class='btn' value='4' on:click={()=>{addDisplay(4)}}><p>4</p></button>
			<button class='btn' value='5' on:click={()=>{addDisplay(5)}}><p>5</p></button>
			<button class='btn' value='6' on:click={()=>{addDisplay(6)}}><p>6</p></button>
			<button class='btn' value='+' on:click={()=>{addDisplay('+')}}><p>+</p></button>
			<button class='btn' value='1' on:click={()=>{addDisplay(1)}}><p>1</p></button>
			<button class='btn' value='2' on:click={()=>{addDisplay(2)}}><p>2</p></button>
			<button class='btn' value='3' on:click={()=>{addDisplay(3)}}><p>3</p></button>
			<button class='btn' value='-' on:click={()=>{addDisplay('-')}}><p>-</p></button>
			<button class='btn' value='.' on:click={()=>{addDisplay('.')}}><p>.</p></button>
			<button class='btn' value='0' on:click={()=>{addDisplay(0)}}><p>0</p></button>
			<button class='btn' value='/' on:click={()=>{addDisplay('/')}}><p>/</p></button>
			<button class='btn' value='*' on:click={()=>{addDisplay('*')}}><p>&times</p></button>
			<button class='reset' value='RESET' on:click={()=>{resetDisplay()}}><p>RESET</p></button>
			<button class='equal' value='=' on:click={()=>{equal('=')}}><p>=</p></button>
		</div>
	</div>
</main>
