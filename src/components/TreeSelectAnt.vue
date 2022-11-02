<script setup lang="ts">
import { TreeSelect } from "ant-design-vue";

// id and values should never be repeated
const treeData = [
	{
		id: "1",
		title: "Produit 11",
		description: "Produit",
		children: [
			{
				id: "P0012C",
				title: "Produit 12",
				description: "Produit",
				children: [{ id: "1-1", title: "test 12", description: "Produit" }],
			},
			{
				id: "P001C",
				title: "Famille 1",
				description: "Famille",
			},
		],
	},
	{
		id: "2",
		title: "disabled",
		description: "disabled",
		disabled: true,
	},
	{
		id: "3",
		title: "checked",
		description: "checked",
		checkable: true,
	},
];
</script>

<template>
	<h1>Ant design Tree select</h1>

	<div class="card">
		<p>
			Edit
			<code>components/TreeSelectAnt.vue</code>
		</p>
	</div>

	<div>
		<!--
			tree-default-expand-all
			treeNodeFilterProp => used property to search
		-->
		<a-tree-select
			style="width: 100%"
			tree-checkable
			:height="233"
			:tree-data="treeData"
			:max-tag-count="10"
			allow-clear
			:field-names="{
				value: 'id',
				title: 'title',
				children: 'children',
			}"
			:showSearch="true"
			notFoundContent="Aucun élément a été trouvé"
			treeNodeFilterProp="title"
		>
			{{ title }}
		</a-tree-select>
	</div>
</template>

<style scoped>
.read-the-docs {
	color: #888;
}
</style>
