<script lang="ts">
	import '../app.postcss';
	import { onMount } from 'svelte';
	import {
		DarkMode,
		Navbar,
		NavBrand,
		NavLi,
		NavUl,
		NavHamburger,
		Button,
		Input
	} from 'flowbite-svelte';
	import {
		Footer,
		FooterBrand,
		FooterLinkGroup,
		FooterLink,
		FooterCopyright,
		FooterIcon
	} from 'flowbite-svelte';
	import '@fontsource/poppins';
	import { isDepsOptimizerEnabled } from 'vite';

	let active = 0;
	let isOpen =false;
	function setActive(index: number) {
		active = index;
	}
	function toggleNavbar() {
		isOpen = !isOpen;
	}

	

	// let breakPoint: number = 1500;
	// let width: number;
	// let activateClickOutside = true;
	// let drawerHidden: boolean = false;
	// $: if (width >= breakPoint) {
	// 	drawerHidden = false;
	// 	activateClickOutside = false;
	// } else {
	// 	drawerHidden = true;
	// 	activateClickOutside = true;
	// }
	// onMount(() => {
	// 	if (width >= breakPoint) {
	// 		drawerHidden = false;
	// 		activateClickOutside = false;
	// 	} else {
	// 		drawerHidden = true;
	// 		activateClickOutside = true;
	// 	}
	// });
	// let darkmodebtn =
	// 	'text-gray-500 dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-gray-700 focus:outline-none focus:ring-4 focus:ring-gray-200 dark:focus:ring-gray-700 rounded-lg text-lg p-2.5  right-2 top-12  md:top-3 md:right-2 z-50';
	// let divClass = 'w-full md:block md:w-auto';
	// let ulClass =
	// 	'flex flex-col p-4 text-center mt-4 md:flex-row md:space-x-8 md:mt-0 md:text-lg md:font-medium';
</script>

<!-- <svelte:window bind:innerWidth={width} /> -->

<header class="sticky shadow-xl dark:shadow-indigo-500/50 top-0 z-50 ">

</header>

<main>
	<slot />
</main>

<Footer customClass="bg-slate-800" footerType="socialmedia">
	<div class="mx-auto max-w-screen-xl text-center">
		<FooterBrand
			href="https://asterisc.in"
			src="/images/logos.webp"
			alt="Asterisc Logo"
			name="Asterisc.in"
			aClass="flex justify-center items-center text-2xl font-semibold text-gray-900 dark:text-white"
		/>
		
		<p class="my-6 text-gray-500 dark:text-gray-400">
			Asterisc Computer Institute is a premier IT education Institute . The institute provides a wide variety of professional career, short term and certification courses, designed by our experts. Our trainers constantly update their technical skills to maintain their expertise.All the courses are taught by certified and experienced faculty. Asterisc computer institute ventured in certification lead IT training ,we have produced highly successful IT professionals working with best IT companies across the globe. Students get placed because of their hardwork and our support and we get business because our students know it better than the most.


		</p>
		<FooterLinkGroup
			ulClass="flex flex-wrap justify-center items-center mb-6 text-gray-900 dark:text-white"
		>
			<FooterLink liClass="" aClass="mr-4 hover:underline md:mr-6" href="/">About Us</FooterLink>
			<FooterLink liClass="" aClass="mr-4 hover:underline md:mr-6" href="/">FAQs</FooterLink>
			<FooterLink liClass="" aClass="mr-4 hover:underline md:mr-6" href="/">Testimonials</FooterLink
			>
			<FooterLink liClass="" aClass="mr-4 hover:underline md:mr-6" href="https://astr-one.vercel.app/">Projects</FooterLink>

			<FooterLink liClass="" aClass="mr-4 hover:underline md:mr-6" href="/">Contact Us</FooterLink>
		</FooterLinkGroup>
		<span class="text-sm text-gray-500 sm:text-center dark:text-gray-400"
			>© 2021-2023 <a href="https://asterisc.in/" class="hover:underline">Asterisc.in™ </a>.
			Developed by Asterisc Technocrat Pvt. Ltd. All Rights Reserved.</span
		>
	</div>
</Footer>



<style>
	p {
		font-family: 'Quicksand', sans-serif;
	}
</style>
