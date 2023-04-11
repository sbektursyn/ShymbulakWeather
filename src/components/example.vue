<template>
	<div class="cards">
		<div class="card"></div>
		<div class="card"></div>
		<div class="card"></div>
	</div>
</template>
<style>
	.cards {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(208px, 1fr));
		gap: 20px;
	}
	.card {
		height: 200px;
		background-color: #4f82f9;
		border-radius: 8px;
	}
</style>