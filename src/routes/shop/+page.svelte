<script>
	import Testimonials from './../../components/Testimonials.svelte';
	import { paginate, LightPaginationNav } from 'svelte-paginate';
	import SearchNormal1 from 'iconsax-svelte/SearchNormal1.svelte';

	let items = [
		{ id: 0, title: 'Modern Sofa', price: 'N163,000', url: '/modern-sofa-2.png' },
		{ id: 1, title: 'Fashion Sneakers', price: 'N71,000', url: '/sneakers.png' },
		{ id: 2, title: 'Modern Sofa', price: 'N160,000', url: '/modern-sofa.png' },
		{ id: 3, title: '8D Audio Gold Headset', price: 'N25,000', url: '/headset.png' },
		{ id: 4, title: 'Multisafe Casual Backpack', price: 'N21,000', url: '/backpack.png' },
		{ id: 5, title: '1-Seater Sofa', price: 'N85,000', url: '/seater.png' },
		{ id: 6, title: 'Maxi 32 INCH LED HD TV', price: 'N92,000', url: '/tv.png' },
		{ id: 7, title: 'Ultra-thin Wireless Mouse 2.4G', price: 'N5,000', url: '/mouse.png' },
		{ id: 8, title: 'Men Casual Top Shirt', price: 'N7,500', url: '/shirt.png' },
		{ id: 9, title: 'Asus E203NA Intel Celeron', price: 'N265,000', url: '/asus.png' },
		{ id: 10, title: '1-Seater Modern sofa', price: 'N48,000', url: '/seat3.png' },
		{ id: 11, title: '72 Samsung Smart TV', price: 'N365,000', url: '/samsung.png' }
	];

	const categories = [
		{ name: 'ceiling', qty: '25' },
		{ name: 'floor', qty: '25' },
		{ name: 'led', qty: '25' },
		{ name: 'modern', qty: '25' },
		{ name: 'retro', qty: '25' },
		{ name: 'wood', qty: '25' }
	];

	const colors = [
		{ name: 'black', qty: '25' },
		{ name: 'blue', qty: '25' },
		{ name: 'red', qty: '25' },
		{ name: 'green', qty: '25' },
		{ name: 'yellow', qty: '25' },
		{ name: 'grey', qty: '25' }
	];

	let currentPage = 1;
	let pageSize = 9;
	$: paginatedItems = paginate({ items, pageSize, currentPage });
</script>

l
<div>
	<div class="flex space-x-10 px-5 lg:px-20 mb-20">
		<div class="lg:w-[80%]">
			<div class="py-5 lg:py-10">
				<p class="capitalize">Showing page {currentPage}</p>
			</div>
			<ul class="md:grid grid-cols-3 md:gap-5 md:space-y-0 space-y-5 pb-10">
				{#each paginatedItems as item}
					<div class="flex flex-col items-center space-y-3">
						<a href={`/shop/${item.id}`}>
							<div class="overflow-hidden md:h-64">
								<img src={item.url} alt={item.title} class="object-cover" />
							</div>
							<h3 class="text-sm font-bold ">{item.title}</h3>
						</a>
						<p class="text-[#ababab]">
							<i class="fas fa-star" />
							<i class="fas fa-star" />
							<i class="fas fa-star" />
							<i class="fas fa-star" />
							<i class="fas fa-star" />
						</p>
						<p class="text-sm text-[#ababab] font-semibold">{item.price}</p>
					</div>
				{/each}
			</ul>

			<LightPaginationNav
				totalItems={items.length}
				{pageSize}
				{currentPage}
				limit={1}
				showStepOptions={true}
				on:setPage={(e) => (currentPage = e.detail.page)}
			/>
		</div>
		<div class="lg:w-[20%]">
			<div class="py-5">
				<div class="flex items-center px-2 py-2 border">
					<input type="text" class="py-2 w-full px-1 outline-none text-secondary" />
					<SearchNormal1 size={24} color="#575757" variant="Linear" />
				</div>
				<div class="mb-10">
					<h3 class="text-lg font-bold py-5">Categories</h3>
					<ul class="space-y-5">
						{#each categories as category}
							<li class="flex items-center space-x-2 capitalize text-[#7E7E7E] font-light">
								{category.name} ({category.qty})
							</li>
						{/each}
					</ul>
				</div>
				<div class="mb-10">
					<h3 class="text-lg font-bold py-5">Color</h3>
					<ul class="space-y-5">
						{#each colors as color}
							<li class="flex items-center space-x-2 capitalize text-[#7E7E7E] font-light">
								{color.name} ({color.qty})
							</li>
						{/each}
					</ul>
				</div>
			</div>
		</div>
	</div>

	<Testimonials />
</div>
