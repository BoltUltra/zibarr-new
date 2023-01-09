<script>
	import Electronics from './Electronics.svelte';
	import { Tab, TabGroup, TabList, TabPanel, TabPanels } from '@rgossiaux/svelte-headlessui';
	import Others from './Others.svelte';

	const accessories = [
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
</script>

<div>
	<div class="text-center text-secondary lg:py-20 py-10 px-5 space-y-3">
		<h3 class="lg:text-5xl text-2xl font-bold">Our latest arrivals</h3>
		<p class="text-sm lg:px-[27rem] text-[#979797]">
			Check out our new arrivals for amazing deals and offers.
		</p>
	</div>

	<!-- Tabs -->
	<TabGroup class="">
		<TabList
			class="mx-5 lg:mx-20 flex mb-5 lg:overflow-hidden overflow-x-scroll space-x-3 lg:space-x-7 pb-2"
		>
			<Tab
				class={({ selected }) =>
					`${selected ? 'selected' : 'border-slate-400'} text-secondary capitalize `}
				>Accessories</Tab
			>
			<Tab
				class={({ selected }) =>
					`${selected ? 'selected' : 'border-slate-400'} text-secondary capitalize `}>hoodies</Tab
			>
			<Tab
				class={({ selected }) =>
					`${selected ? 'selected' : 'border-slate-400'} text-secondary capitalize`}>tshirts</Tab
			>
			<Tab
				class={({ selected }) =>
					`${selected ? 'selected' : 'border-slate-400'} text-secondary capitalize`}>Vests</Tab
			>
			<Tab
				class={({ selected }) =>
					`${selected ? 'selected' : 'border-slate-400'} text-secondary capitalize `}>Shirts</Tab
			>
			<Tab
				class={({ selected }) =>
					`${selected ? 'selected' : 'border-slate-400'} text-secondary capitalize `}>Blazers</Tab
			>
			<Tab
				class={({ selected }) =>
					`${selected ? 'selected' : 'border-slate-400'} text-secondary capitalize `}>Suits</Tab
			>
		</TabList>
		<TabPanels>
			<TabPanel class="text-secondary">
				<p class="text-right capitalize pb-5 text-xs pr-5 lg:pr-20">
					showing {accessories.length}
					{accessories.length > 1 ? `products` : `product`}
				</p>
				<div class="md:grid grid-cols-4 md:gap-5 md:space-y-0 space-y-5 px-5 lg:px-20">
					{#each accessories as accessory}
						<div class="flex flex-col items-center space-y-3">
							<div class="overflow-hidden md:h-64">
								<img src={accessory.url} alt={accessory.title} class="object-cover" />
							</div>
							<h3 class="text-sm font-bold ">{accessory.title}</h3>
							<p class="text-[#ababab]">
								<i class="fas fa-star" />
								<i class="fas fa-star" />
								<i class="fas fa-star" />
								<i class="fas fa-star" />
								<i class="fas fa-star" />
							</p>
							<p class="text-sm text-[#ababab] font-semibold">{accessory.price}</p>
						</div>
					{/each}
				</div>
				<Others />
				<div class="">
					<Electronics />
				</div>
			</TabPanel>
			<TabPanel class="px-5 text-secondary">oga</TabPanel>
		</TabPanels>
	</TabGroup>
</div>
