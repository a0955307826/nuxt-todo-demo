<template>
	<div class="container">
		<div class="box" v-for="item in 5" :key="item"></div>
	</div>
</template>

<script setup></script>

<style lang="scss" scoped>
.box {
	width: 100%;
	height: 300px;
	border: solid 1px black;
	background-color: lightgreen;
}
</style>
