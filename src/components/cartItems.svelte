<script>
	import Add from 'iconsax-svelte/Add.svelte';
	import Minus from 'iconsax-svelte/Minus.svelte';
	import Trash from 'iconsax-svelte/Trash.svelte';
	const items = [
		{
			product: 'Tee-shirt ZEUS Réflective – Blanc',
			color: 'Orange',
			size: 'XL',
			price: 70,
			imgURL: '/checkout1.png'
		},
		{
			product: 'Drop The Label baseball tee-shirt',
			color: 'Pink',
			size: 'S',
			price: 21,
			imgURL: '/checkout2.png'
		},
		{
			product: 'T-shirt with Printed Design',
			color: 'Gray',
			size: 'L',
			price: 72,
			imgURL: '/checkout3.png'
		}
	];

	let subTotalPrice = items.reduce(function (prev, cur) {
		return prev + cur.price;
	}, 0);

	let delivery = Math.round(subTotalPrice * 0.1);
	let total = subTotalPrice + delivery;

	let num = 1;
	const add = () => {
		num += 1;
	};
	const minus = () => {
		num -= 1;
		if (num < 1) {
			num = 1;
		}
	};
</script>

<div class="lg:pl-10">
	{#each items as item}
		<div class="flex lg:flex-row flex-col border-b py-5 lg:space-x-5">
			<div class="flex items-start space-x-5">
				<img src={item.imgURL} alt="" class="lg:w-44 w-32" />
				<div class="flex flex-col">
					<p class="text-sm pb-5">{item.product}</p>
					<span class="text-xs text-[#575757]">Color: {item.color}</span>
					<span class="text-xs text-[#575757]">Size: {item.size}</span>
					<span class="text-xs text-[#575757] font-semibold mt-5">Total: ${item.price}</span>
				</div>
			</div>
			<div class="flex lg:flex-col items-center justify-between lg:mt-0 mt-5">
				<div class="flex items-center space-x-5 border rounded-full text-xs">
					<button on:click={minus} class="border-r p-2">
						<Minus size={12} color="#575757" variant="Linear" />
					</button>
					<span>{num}</span>
					<button on:click={add} class="border-l p-2">
						<Add size={12} color="#575757" variant="Linear" />
					</button>
				</div>
				<div class="flex items-center space-x-3 text-xs text-secondary">
					<Trash size={16} color="#575757" variant="Linear" />
					<span>Remove</span>
				</div>
			</div>
		</div>
	{/each}
	<div class="flex flex-col text-right justify-center mr-10 text-sm space-y-2 my-10">
		<p><span class="text-gray-200 uppercase">Sub-total: </span>${subTotalPrice}</p>
		<p><span class="text-gray-200 uppercase">Delivery: </span>${delivery}</p>
		<p><span class="text-gray-200 uppercase">Total: </span>${total}</p>
	</div>
</div>
