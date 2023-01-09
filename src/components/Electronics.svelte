<script>
	const electronics = [
		{ id: 0, title: 'Asus E203NA Intel Celeron', price: 'N172,000', url: '/asus.png' },
		{ id: 1, title: '17’ M1 Macbook Pro 2020', price: 'N1,213,000', url: '/macbook.png' },
		{ id: 2, title: 'TCL 32" DLED HD TV', price: 'N977,000', url: '/dled.png' },
		{ id: 3, title: '68Watts M206BT Speakers', price: 'N37,000', url: '/speakers.png' },
		{ id: 4, title: 'Wireless Lavalier Microphone', price: 'N16,350', url: '/microphone.png' },
		{ id: 5, title: '4KVA/48V INVERTER', price: 'N1,321,000', url: '/inverter.png' },
		{ id: 6, title: 'Century 20L Electric Oven', price: 'N35,000', url: '/oven.png' },
		{ id: 7, title: 'Scanfrost 32-Inch LED TV', price: 'N123,580', url: '/led-tv.png' }
	];
</script>

<div>
	<div class="text-center text-secondary lg:py-20 py-10 px-5 space-y-3">
		<h3 class="lg:text-5xl text-2xl font-bold">Our latest arrivals</h3>
		<p class="text-sm lg:px-[27rem] text-[#979797]">
			Check out our new arrivals for amazing deals and offers.
		</p>
	</div>

	<div class="md:grid grid-cols-4 md:gap-5 md:space-y-0 space-y-5 px-5 lg:px-20">
		{#each electronics as electronic}
			<div class="flex flex-col items-center space-y-3">
				<div class="">
					<img src={electronic.url} alt={electronic.title} class="" />
				</div>
				<h3 class="text-sm font-bold ">{electronic.title}</h3>
				<p class="text-[#ababab]">
					<i class="fas fa-star" />
					<i class="fas fa-star" />
					<i class="fas fa-star" />
					<i class="fas fa-star" />
					<i class="fas fa-star" />
				</p>
				<p class="text-sm text-[#ababab] font-semibold">{electronic.price}</p>
			</div>
		{/each}
	</div>
</div>
