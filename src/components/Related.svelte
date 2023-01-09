<script>
	const relatedProducts = [
		{ title: 'Modern Sofa', imgURL: '/related1.png' },
		{ title: 'Modern Sofa', imgURL: '/related2.png' },
		{ title: 'Modern Sofa', imgURL: '/related3.png' },
		{ title: 'Modern Sofa', imgURL: '/related4.png' }
	];
</script>

<div class="my-10">
	<h3 class="font-semibold text-xl py-5">Related Products</h3>
	<div class="lg:grid grid-cols-4 justify-center lg:gap-5">
		{#each relatedProducts as product}
			<div class="flex flex-col items-center justify-between space-y-2 md:space-y-3 lg:mb-0 mb-5">
				<img src={product.imgURL} alt="" class="" />
				<span class="font-semibold">{product.title}</span>
				<p class="text-[#ababab]">
					<i class="fas fa-star" />
					<i class="fas fa-star" />
					<i class="fas fa-star" />
					<i class="fas fa-star" />
					<i class="fas fa-star" />
				</p>
			</div>
		{/each}
	</div>
</div>
