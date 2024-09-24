<script setup>
import ProductCard from '@/components/ProductCard.vue'
import Pagination from '@/components/Pagination.vue';
import { onBeforeMount, onBeforeUnmount, onBeforeUpdate, onMounted, onUnmounted, onUpdated, ref } from 'vue';

const page = ref(1);

function nextPage(){
  page.value += 1;
}

onBeforeMount(() => {
  console.log('Component will be mounted soon');
});

onMounted(() => {
  console.log('Component has been mounted');
});

onBeforeUpdate(() => {
	console.log('Component will be updated');
});

onUpdated(()=>{
  console.log('Component updated');
});

onBeforeUnmount(() => {
  console.log('The component will be deleted soon');
})

onUnmounted(() => {
  console.log('The component already deleted');
});

</script>
<template>
	<main>
    {{ page }}
    <button @click="nextPage">Next</button>
		<div class="product-grid">
      <ProductCard></ProductCard>
		</div>
		<div class="pagination">
			<Pagination></Pagination>
		</div>
	</main>
</template>

<style scoped>
.product-grid {
	display: grid;
	grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
	gap: 20px;
	width: 80%;
	margin: 0 auto;
}
.pagination {
	display: flex;
	justify-content: center;
	align-items: center;
	margin-top: 20px;
}
</style>