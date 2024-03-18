<template>
	<section class="to-do">
		<input
			type="text"
			@keyup.enter="add_todo"
			v-model="new_todo"
			placeholder="待辦事項"
		/>
		<button class="btn-add" @click="add_todo">新增</button>
	</section>
	<ul>
		<li v-for="(list, index) in save_to_do_list" :key="`list-${index}`">
			{{ list }}
			<button class="btn-delete" @click="delete_todo(index)">刪除</button>
		</li>
	</ul>
</template>

<script setup>
const new_todo = ref("");
const save_to_do_list = reactive([]);

const add_todo = () => {
	if (new_todo.value.trim() !== "") {
		save_to_do_list.push(new_todo.value);
		new_todo.value = "";
	}
};

const delete_todo = (index) => {
	save_to_do_list.splice(index, 1);
};
</script>

<style lang="scss" scoped>
.to-do {
	display: flex;
	align-items: center;
	gap: 10px;
}

.btn-delete {
	margin-left: 10px;
}

ul {
	display: grid;
	gap: 10px;
}
</style>
