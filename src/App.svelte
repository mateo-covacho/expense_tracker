<script>
	import Expensehistory from "./components/Expensehistory.svelte"

	let transaction_name
	let transaction_value 

	$: transaction_name, transaction_value


	let transactions = [
		{
			id: 0,
			name: 'Bar',
			value: '54$'
		},
	
		{
			id: 1,
			name: 'Food',
			value: '34$'
		},
	
		{
			id: 2,
			name: 'Desk',
			value: '21$'
		},
	
		{
			id: 3,
			name: 'Keyboard',
			value: '63$'
		},
	
	]
	
	console.log(transactions)

	function new_Transaction() {
		transactions = [...transactions ,{			
			id: transactions.length ,
			name: transaction_name ,
			value: transaction_value + "$"
		}]
	
		console.log(transactions)
		transaction_name = "";
		transaction_value = "";
	
	};


</script>

<main>
	<h1>Track your expenses</h1>
	
	<div class="input_section">

		<h2 >New transaction name</h2>
		<input bind:value={transaction_name} class="input_name">

		<br>
		<br>

		<h2 >New transaction value</h2>
		<input type="number" bind:value={transaction_value} class="input_name">

		<br>
		<br>
		<br>


		<button on:click={new_Transaction}>New transaction</button>
		<br>
		<br>
		<br>

	</div>

	<div class="transaction_history">
		<Expensehistory {transactions}/>
	</div>
</main>

<style>

	

	main {
		text-align: center;
		padding: 1em;
		margin: 0 auto;

	}



	h1 {
		color: #ff3e00;
		font-size: 4em;
		font-weight: 200;


	}


	.input_section h2 {
		text-align: left;
		width: 100%;
		margin: 0;
		font-family:-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
		font-weight: 400;
		font-size: 2vw;
		padding-top: 2vw;

	}

	.input_section {
		background-image: linear-gradient(to bottom left,#7209B7, #B5179E);
		width: 30vw;
		margin: 0 10vw;
		padding: 2vh;
		margin-right: 0;
		border: 2px;
 		border-radius: 20px;
		display: inline-table;
	}

	.transaction_history {
		background-image: linear-gradient(to bottom right,#7209B7, #B5179E);
		width: 30vw;
		padding: 2vh;
		border: 2px;
 		border-radius: 20px;
		display: inline-table;
		vertical-align: top;
		

	}

	.input_name {
		float: left;


	}

	button {
		float: left;


	}

	input {
		width: 70%;
	}
</style>

