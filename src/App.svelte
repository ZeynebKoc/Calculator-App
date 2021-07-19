<script>
	let display = 0;
	let firstOperand = null;
	let secondOperand = false;
	let operator = null;
	let operatorClicked = false;

	const addDisplay = (num) => {
		if(display === 0 || operatorClicked ) {
			display = '';	
		}
		if(display.length <= 13){
			display += String(num);	
		}
		operatorClicked = false;
	}

	const dot = () => {
		if(display == 0) {
			display = '0.';
		}else if(!display.includes('.')){
			display += '.';
		}	
	}

	const resetDisplay = () => {
		display = 0;
	}

	const deleteNum = () => {
		display = String(display);
		if(display.length <= 1) { 
			display = 0;
		}else if (display == /.$/) {
			display = display.slice(0, -2); 
		}else{
			display = display.slice(0, -1);
		}	
	}	
	
	const equal = () => {
		//debugger;
		secondOperand = Number(display)
		if(operator === '+'){
		 	display = firstOperand + secondOperand;
			display = display.toFixed(7).replace(/0+$/, '');
		}else if(operator === '-'){
		 	display =  firstOperand - secondOperand;
			display = display.toFixed(7).replace(/0+$/, '');
		}else if(operator === '*'){
		 	display =  firstOperand * secondOperand;
			display = display.toFixed(7).replace(/0+$/, '');
		}else if(operator === '/'){
		 	display =  firstOperand / secondOperand;
			display = display.toFixed(7).replace(/0+$/, '');
		}
	} 

	const operationsState = (operation) => {
		if(secondOperand, operatorClicked = true){
			equal();
		}
		operatorClicked = true;
		firstOperand = Number(display);
		operator = operation;
	}
	
	//switch theme
	const changeTheme = (e) => {
		let oldlink = document.getElementsByTagName("link")[0];
		oldlink.setAttribute("href", `./themes/theme${e.target.value}.css`);
	}
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
				<input on:change={changeTheme} type="range" class="range" min=1 max=3 step="1" value='1' />
			</div>
		</div>
	</div>
	
	<div class='display' data-test-id="display" >
		<div class="display-text" disabled>{display}</div> 
	</div> 
	
	<div class='keypad'>
		<div class='container'>
			<button class='btn' value='7' on:click={()=>{addDisplay(7)}}>7</button>
			<button class='btn' value='8'on:click={()=>{addDisplay(8)}}>8</button>
			<button class='btn' value='9' on:click={()=>{addDisplay(9)}}>9</button>
			<button class='del' value='DEL' on:click={()=>{deleteNum()}}>DEL</button>
			<button class='btn' value='4' on:click={()=>{addDisplay(4)}}>4</button>
			<button class='btn' value='5' on:click={()=>{addDisplay(5)}}>5</button>
			<button class='btn' value='6' on:click={()=>{addDisplay(6)}}>6</button>
			<button class='btn' value='+' on:click={()=>{operationsState('+')}}>+</button>
			<button class='btn' value='1' on:click={()=>{addDisplay(1)}}>1</button>
			<button class='btn' value='2' on:click={()=>{addDisplay(2)}}>2</button>
			<button class='btn' value='3' on:click={()=>{addDisplay(3)}}>3</button>
			<button class='btn' value='-' on:click={()=>{operationsState('-')}}>-</button>
			<button class='btn' value='.' on:click={()=>{dot()}}>.</button>
			<button class='btn' value='0' on:click={()=>{addDisplay(0)}}>0</button>
			<button class='btn' value='/' on:click={()=>{operationsState('/')}}>/</button>
			<button class='btn' value='*' on:click={()=>{operationsState('*')}}>&times</button>
			<button class='reset' value='RESET' on:click={()=>{resetDisplay()}}>RESET</button>
			<button class='equal' value='=' on:click={()=> equal()}>=</button>
		</div>
	</div>
</main>