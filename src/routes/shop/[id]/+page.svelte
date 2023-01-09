<script>
	import Related from './../../../components/Related.svelte';
	import ArrowLeft1 from 'iconsax-svelte/ArrowLeft1.svelte';
	import ArrowRight1 from 'iconsax-svelte/ArrowRight1.svelte';
	import Heart from 'iconsax-svelte/Heart.svelte';
	import { Tab, TabGroup, TabList, TabPanel, TabPanels } from '@rgossiaux/svelte-headlessui';
	let num = 0;
	const add = () => {
		num += 1;
	};
	const minus = () => {
		num -= 1;
	};

	let active = false;
	const toggle = () => {
		active = !active;
	};
</script>

<div class="px-20">
	<p class="py-10">shop/sofa code 234</p>

	<div class="flex space-x-5 items-center">
		<div class="flex items-center space-x-5 w-[60%]">
			<div class="flex flex-col space-y-5">
				<div><img src="/dyn2.png" alt="" class="w-60" /></div>
				<div><img src="/dyn2.png" alt="" class="w-60" /></div>
				<div><img src="/dyn2.png" alt="" class="w-60" /></div>
				<div><img src="/dyn2.png" alt="" class="w-60" /></div>
			</div>
			<div><img src="/dyn1.png" alt="" /></div>
		</div>
		<div class="w-[40%]">
			<div class="flex flex-col space-y-3">
				<p class="font-bold text-xl">Sofa code 234</p>
				<p class="text-[#ababab]">
					<i class="fas fa-star" />
					<i class="fas fa-star" />
					<i class="fas fa-star" />
					<i class="fas fa-star" />
					<i class="fas fa-star" /> (top)
				</p>
				<p class="space-x-2">
					<span class="line-through text-xs font-light">$256,00</span>
					<span>$125,00</span>
				</p>
			</div>
			<p class="my-10">
				Lorem ipsum dolor sit amet, consectetur adipiscing elit. Enim et volutpat lobortis enim
				donec adipiscing nibh. Consectetur in ac elementum aliquam imperdiet tellus.
			</p>
			<div class="flex items-center justify-between mb-10">
				<div class="flex items-center space-x-10 border p-5 max-w-6xl">
					<button on:click={minus}>
						<ArrowLeft1 size={16} color="#575757" variant="Linear" />
					</button>
					<span>{num}</span>
					<button on:click={add}>
						<ArrowRight1 size={16} color="#575757" variant="Linear" />
					</button>
				</div>
				<button
					class="bg-secondary py-5 px-10 text-white hover:bg-black transition-colors duration-300"
					>Add to cart</button
				>
			</div>
			<div class="text-[#575757] flex items-center space-x-5 my-10">
				<button on:click={toggle}>
					<Heart
						size={24}
						color={active ? '#ff0000' : '#575757'}
						variant={active ? 'Bold' : 'Linear'}
					/>
				</button>
				<span on:click={toggle} class="cursor-pointer">Add to wishlist</span>
			</div>
			<div class="mb-10 text-[#575757] space-y-5 text-sm">
				<p>Sku: 02</p>
				<p>Category: Sofa</p>
				<p>Tags: Sofa, clean</p>
			</div>
			<TabGroup class="text-[#575757] my-5">
				<TabList class="flex mb-5 space-x-3 lg:space-x-7 pb-2">
					<Tab
						class={({ selected }) =>
							`${selected ? 'selected' : 'border-slate-400'} text-secondary capitalize `}
						>Description</Tab
					>
					<Tab
						class={({ selected }) =>
							`${selected ? 'selected' : 'border-slate-400'} text-secondary capitalize `}
						>Additional informatiom</Tab
					>
					<Tab
						class={({ selected }) =>
							`${selected ? 'selected' : 'border-slate-400'} text-secondary capitalize`}
						>Preview</Tab
					>
				</TabList>
				<TabPanels>
					<TabPanel class="">
						<p>
							Lorem ipsum dolor sit amet, consectetur adipiscing elit. Enim et volutpat lobortis
							enim donec adipiscing nibh. Consectetur in ac elementum aliquam imperdiet tellus.
						</p>
					</TabPanel>
					<TabPanel class="">
						<p>
							Lorem ipsum dolor sit amet, consectetur adipiscing elit. Enim et volutpat lobortis
							enim donec adipiscing nibh. Consectetur in ac elementum aliquam imperdiet tellus.
						</p>
					</TabPanel>
					<TabPanel class="">
						<p>
							Lorem ipsum dolor sit amet, consectetur adipiscing elit. Enim et volutpat lobortis
							enim donec adipiscing nibh. Consectetur in ac elementum aliquam imperdiet tellus.
						</p>
					</TabPanel>
				</TabPanels>
			</TabGroup>
		</div>
	</div>

	<Related />
</div>
