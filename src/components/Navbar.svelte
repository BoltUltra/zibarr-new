<script>
	import Menu from 'iconsax-svelte/Menu.svelte';
	import SearchNormal1 from 'iconsax-svelte/SearchNormal1.svelte';
	import Bag2 from 'iconsax-svelte/Bag2.svelte';
	let isNavOpen = false;

	const handleNavMenu = () => {
		isNavOpen = !isNavOpen;
	};
</script>

<nav class="flex items-center justify-between lg:px-16 px-5 py-5">
	<div class="flex items-center space-x-10 text-secondary">
		<a href="/"> <img src="/logo.png" alt="" class="lg:w-32 w-24" /></a>
		<ul class="space-x-5 md:flex hidden font-semibold">
			<a href="/"><li>Home</li></a>
			<a href="/shop"><li>Shop</li></a>
			<li>About us</li>
			<li>Blog</li>
		</ul>
	</div>
	<div class="md:block hidden">
		<div class="flex items-center space-x-5">
			<SearchNormal1 size={24} color="#575757" variant="Linear" />
			<Bag2 size={24} color="#575757" variant="Linear" />
			<Menu size={24} color="#575757" variant="Linear" />
		</div>
	</div>
	<div class="space-x-5 flex items-center md:hidden">
		<SearchNormal1 size={24} color="#575757" variant="Linear" />
		<button class="" on:click={handleNavMenu}>
			<Menu size={24} color="#575757" variant="Linear" />
		</button>
	</div>
</nav>
<div class="md:hidden px-5">
	<div class={isNavOpen ? 'block' : 'hidden'}>
		<ul class="space-y-3 text-primary-500">
			<li>Home</li>
			<li>Shop</li>
			<li>About us</li>
			<li>Blog</li>
		</ul>
	</div>
</div>
