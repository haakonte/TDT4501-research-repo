<svelte:head>
	<title>Memory</title>
	<meta name="memory" content="Memory game" />
</svelte:head>

<script>

	let count = 0;
	let grid = [[1, 2, 3],[1, 2, 3],[1, 2, 3],[1, 2, 3]];

	$: countChecker = count > 10 ? 'Oii du har talt over 10 ganger ' : '';

</script>

<div class="header">

	<h1>Velkommen til minne spillet</h1>

	<h2>Dette spillet skal være en øvelse i å lage en svelte-app</h2>

</div>


<div class="container">


	<div class="text-column">


		<p>
			Her skal jeg starte med en enkel counter, den er her: {count}
		</p>

		<div class="buttons">

			<button on:click={() => count += 1}>
				Øk med 1
			</button>

			<button on:click={() => count = 0}>
				Reset knappen
			</button>

			<button on:click={() => count -= 1}>
				Reduser med 1
			</button>
		</div>

		<div style="display:flex; justify-content:center; margin: 20px;">
			{countChecker}
		</div>
	</div>

	<div class="memory-game-container">
		<div style="font-weight:bold; margin: 15px">
		Heisann! Her er memory spillet. <br>Trykk på en av cellene for å åpne den.<br>
		Forsøk deretter å matche en til og få like.
		</div>
		<div class="memory-game">
			{#each grid as row}
				<div class="row">
					{#each row as cell}
						<div class="cell">
							{cell}
						</div>
					{/each}
				</div>
			{/each}
		</div>
	</div>
</div>

<style>

	.memory-game-container {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
		border: 1px solid black;
	}

	.row {
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
	}

	.cell {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		border: 1px solid black;
		margin: 5px;
		width: 75px;
		height: 100px;
	}

	.container {
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
	}

	.header {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.4;
	}
	h2 {
		
		font-size: 1.5em;
	}

	button {
		font-size: 1.5em;
		width: 200px;
		height: 75px;
		background-color: #150b59;
		color: #fffdf0;
		border: none;
		margin: 10px;
		border-radius: 10px;
	}

	button:hover {
		background-color: #fffdf0;
		color: #150b59;
	}

	.buttons {
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: center;

	}


</style>