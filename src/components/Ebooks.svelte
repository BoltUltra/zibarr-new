<script>
	import ArrowRight1 from 'iconsax-svelte/ArrowRight1.svelte';

	const books = [
		{
			id: 1,
			title: 'The Money Chemical Equation',
			author: 'Sam Harvard',
			price: 'N15,000',
			imgURL: '/chemical.png'
		},
		{
			id: 2,
			title: 'The Money Magnet Writer',
			author: 'Odunayo Tobiloba Sonde',
			price: 'N8,000',
			imgURL: '/magnet.png'
		},
		{
			id: 3,
			title: 'Living Unchained',
			author: 'Odun Sonde',
			price: 'FREE',
			imgURL: '/unchained.png'
		},
		{
			id: 4,
			title: 'Make Your Money Find You',
			author: 'Dr. Olu Ayoola',
			price: 'N5,000',
			imgURL: '/find.png'
		}
	];
</script>

<section class="py-10">
	<div class="text-center mb-10">
		<h3 class="font-bold md:text-3xl">Ebooks and paperbacks</h3>
		<p class="text-[#979797] md:text-sm">Explore our digital and paperback book store.</p>
	</div>

	<div class="grid grid-cols-1 md:grid-cols-2 gap-10 md:px-20">
		{#each books as book}
			<div class="">
				<div class="space-y-5">
					<img src={book.imgURL} alt="" class="object-cover" />
					<div class="md:text-left text-center space-y-3">
						<h3 class="font-bold">{book.title}</h3>
						<p class="text-[#979797]">Author: {book.author}</p>
						<p class="font-bold">{book.price}</p>
					</div>
				</div>
			</div>
		{/each}
	</div>
	<div class="flex justify-center py-10">
		<button
			class="flex items-center space-x-3 text-primary border border-primary py-3 px-5 text-sm md:mx-0 mx-auto"
		>
			<span>View more</span>
			<ArrowRight1 size={16} color="#979797" variant="Linear" />
		</button>
	</div>
</section>
