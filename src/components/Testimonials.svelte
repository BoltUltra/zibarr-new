<script>
	import { Swiper, SwiperSlide } from 'swiper/svelte';

	// Import Swiper styles
	import 'swiper/css';

	import 'swiper/css/navigation';

	import '../swiper.css';

	// import required modules
	import { Navigation } from 'swiper';
	let quote =
		'I have never experienced anything this good. Zibarr has helped me boost my sales. All I do is upload my products and sit back while their affiliates sell for me.';

	const testimonials = [
		{
			quote,
			name: 'Ablad Bruce',
			role: 'Course Creator/Tutor'
		},
		{
			quote,
			name: 'Soroush Norozy',
			role: 'Designer'
		},
		{
			quote,
			name: 'Ablad Bruce',
			role: 'Course Creator/Tutor'
		},
		{
			quote,
			name: 'Soroush Norozy',
			role: 'Designer'
		},
		{
			quote,
			name: 'Ablad Bruce',
			role: 'Course Creator/Tutor'
		},
		{
			quote,
			name: 'Soroush Norozy',
			role: 'Designer'
		},
		{
			quote,
			name: 'Ablad Bruce',
			role: 'Course Creator/Tutor'
		},
		{
			quote,
			name: 'Soroush Norozy',
			role: 'Designer'
		}
	];
</script>

<div>
	<Swiper navigation={true} modules={[Navigation]} class="mySwiper bg-[#efefef]">
		{#each testimonials as testimonial}
			<SwiperSlide>
				<div class="py-5">
					<p class="font-bold text-6xl text-center">"</p>
					<div class="space-y-3 mx-10 lg:mx-[30rem]">
						<p class="lg:text-lg text-sm text-[#ababab] px-5">
							{testimonial.quote}
						</p>
						<p class="text-sm font-semibold">{testimonial.name}</p>
						<p class="text-xs">{testimonial.role}</p>
					</div>
				</div>
			</SwiperSlide>
		{/each}
	</Swiper>
</div>
