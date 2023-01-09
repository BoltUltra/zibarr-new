<script>
	const blogpost = [
		{
			date: '29 Sept. 2022',
			author: 'Soroush Norozy',
			title: 'Your office should have only natural materials',
			imgURL: '/blogpost1.png'
		},
		{
			date: '29 Sept. 2022',
			author: 'Soroush Norozy',
			title: 'Your office should have only natural materials',
			imgURL: '/blogpost2.png'
		}
	];
</script>

<div class="px-5">
	<div class="lg:flex lg:px-20 justify-center lg:space-x-10">
		{#each blogpost as post}
			<div class="flex flex-col items-center justify-between space-y-2 md:space-y-3 mb-5">
				<img src={post.imgURL} alt="" class="" />
				<div class="flex flex-col space-y-2">
					<p class="text-secondary text-xs">{post.date} by {post.author}</p>
				</div>
				<div class="flex flex-col space-y-3">
					<p class="text-secondary font-semibold text-center">{post.title}</p>
					<button class="text-secondary border border-secondary py-3 px-10 text-sm">
						Read more
					</button>
				</div>
			</div>
		{/each}
	</div>
</div>
