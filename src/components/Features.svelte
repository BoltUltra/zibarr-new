<script>
	import Clock1 from 'iconsax-svelte/Clock1.svelte';
	import Bag2 from 'iconsax-svelte/Bag2.svelte';
	import Card from 'iconsax-svelte/Card.svelte';
	import DollarCircle from 'iconsax-svelte/DollarCircle.svelte';
</script>

<div class="lg:px-20 px-5 lg:space-y-0 space-y-5 text-secondary py-10 lg:grid grid-cols-4 lg:gap-5">
	<div class="space-y-3">
		<div class="flex items-center space-x-3">
			<Clock1 size={32} color="#000" variant="Linear" />
			<p class="font-semibold text-2xl">Upload Products</p>
		</div>
		<p class="text-[#ABABAB]">
			Zibarr vendors have 24/7 access and can upload their physical and digital products for sale.
		</p>
	</div>
	<div class="space-y-3">
		<div class="flex items-center space-x-3">
			<Bag2 size={32} color="#000" variant="Linear" />
			<p class="font-semibold text-2xl">Affiliate Marketers</p>
		</div>
		<p class="text-[#ABABAB]">
			You dont have to worry about marketing your products by yourself. Zibarr’s wide affiliate
			network will handle that FOR FREE.
		</p>
	</div>
	<div class="space-y-3">
		<div class="flex items-center space-x-3">
			<Card size={32} color="#000" variant="Linear" />
			<p class="font-semibold text-2xl">Track Sales</p>
		</div>
		<p class="text-[#ABABAB]">
			Stay in the know with real time stats on your performance as a vendor. Track your sales,
			reviews, commissions and manage your resources from one dashboard.
		</p>
	</div>
	<div class="space-y-3">
		<div class="flex items-center space-x-3">
			<DollarCircle size={32} color="#000" variant="Linear" />
			<p class="font-semibold text-2xl">Payment</p>
		</div>
		<p class="text-[#ABABAB]">
			Set up your withdrawal wallet in easy-to-follow steps. Receive your due payments immediately
			to request for them.
		</p>
	</div>
</div>
