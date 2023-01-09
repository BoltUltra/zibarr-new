<script>
	import ArrowRight1 from 'iconsax-svelte/ArrowRight1.svelte';
</script>

<div
	class="my-5 bg-[#3D3838] text-white flex md:flex-row flex-col items-center justify-around md:py-3 py-10 lg:space-y-0 space-y-5 lg:space-x-10 lg:text-2xl text-lg md:text-left text-center"
>
	<div class="space-y-5">
		<p class="">
			Take affordable quality courses and <br /><span class="font-semibold text-[#FFEC86]"
				>learn at your own pace.</span
			>
		</p>
		<button
			class="flex items-center space-x-3 text-[#FFEC86] border border-[#FFEC86] py-3 px-5 text-sm md:mx-0 mx-auto"
		>
			<span>View more</span>
			<ArrowRight1 size={16} color="#FFEC86" variant="Linear" />
		</button>
	</div>
	<img src="/course.png" alt="" class="" />
</div>
