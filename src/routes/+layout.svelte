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

	let active = 0;

	function setActive(index: number) {
		active = index;
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
	let darkmodebtn =
		'text-gray-500 dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-gray-700 focus:outline-none focus:ring-4 focus:ring-gray-200 dark:focus:ring-gray-700 rounded-lg text-lg p-2.5  right-2 top-12  md:top-3 md:right-2 z-50';
	let divClass = 'w-full md:block md:w-auto';
	let ulClass =
		'flex flex-col p-4 text-center mt-4 md:flex-row md:space-x-8 md:mt-0 md:text-lg md:font-medium';
</script>

<!-- <svelte:window bind:innerWidth={width} /> -->

<header class="sticky shadow-xl dark:shadow-indigo-500/50 top-0 z-50 ">

	<Navbar let:hidden let:toggle>
		<NavBrand href="/">
		  <img
			src="https://flowbite.com/docs/images/logo.svg"
			class="mr-3 h-6 sm:h-9"
			alt="Flowbite Logo"
		  />
		  <span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white">
			Flowbite
		  </span>
		</NavBrand>
		<div class="flex md:order-2">
		  <Button color="none" data-collapse-toggle="mobile-menu-3" aria-controls="mobile-menu-3" aria-expanded="false" class="md:hidden text-gray-500 dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-gray-700 focus:outline-none focus:ring-4 focus:ring-gray-200 dark:focus:ring-gray-700 rounded-lg text-sm p-2.5 mr-1" >
			<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 dark:text-white"><path stroke-linecap="round" stroke-linejoin="round" d="M21 21l-5.197-5.197m0 0A7.5 7.5 0 105.196 5.196a7.5 7.5 0 0010.607 10.607z" /></svg>
		  </Button>
		  <div class="hidden relative md:block">
			<div class="flex absolute inset-y-0 left-0 items-center pl-3 pointer-events-none">
			  <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 dark:text-white"><path stroke-linecap="round" stroke-linejoin="round" d="M21 21l-5.197-5.197m0 0A7.5 7.5 0 105.196 5.196a7.5 7.5 0 0010.607 10.607z" /></svg>
			</div>
			<Input id="search-navbar" class="pl-10" placeholder="Search..." />
		  </div>
		  <NavHamburger on:click={toggle} />
		</div>
		<NavUl {hidden}>
		  <NavLi href="/" active={true}>Home</NavLi>
		  <NavLi href="/about">About</NavLi>
		  <NavLi href="/services">Services</NavLi>
		</NavUl>
	  </Navbar>

	<Navbar let:hidden let:toggle fluid class="">
		<NavBrand href="/" class="">
			<img
				src="/images/logos.webp"
				class="h-auto flex w-9 md:w-9 lg:w-9"
				alt="mission"
			/>
			<span class="self-center whitespace-nowrap flex text-base md:text-2xl   dark:text-white ">
				<p class="text-2xl">Asterisc.in</p>
			</span>
		</NavBrand>
		<div class="flex md:order-2">
			<!-- <a href="/contactus" class="mt-1 bg-purple-600" ><Button size="sm" >Contact Us</Button></a> -->
			<a
							href="/contactus"
							class="rounded-md bg-purple-600 px-3.5 py-2.5 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
							>Contact Us</a
						>
			<DarkMode class="ml-2" btnClass={darkmodebtn} />
			<NavHamburger on:click={toggle} />
		</div>

		<NavUl {hidden} {divClass} {ulClass}>
			<NavLi on:click={toggle} href="/" active={active === 0} on:click={() => setActive(0)}><p class=" text-base  md:text-xl">Home</p></NavLi>
			<NavLi on:click={toggle} href="/aboutus" active={active === 1} on:click={() => setActive(1)}><p class="text-base md:text-xl">About Us</p></NavLi>
			<NavLi on:click={toggle} href="/courses" active={active === 2} on:click={() => setActive(2)}><p class="text-base md:text-xl">Courses</p></NavLi>
			<NavLi on:click={toggle} href="/faqs" active={active === 3} on:click={() => setActive(3)}><p class="text-base md:text-xl">FAQ</p></NavLi>
			<NavLi on:click={toggle} href="/testimonials" active={active === 4} on:click={() => setActive(4)}
				><p class="text-base md:text-xl">Testimonials</p></NavLi
			>
			<NavLi on:click={toggle} href="https://astr-one.vercel.app/" active={active === 5} on:click={() => setActive(5)}><p class="text-base md:text-xl">Projects</p></NavLi>
			<NavLi on:click={toggle} href="/contactus" active={active ===6} on:click={() => setActive(6)}><p class="text-base md:text-xl">Contact Us</p></NavLi>
		</NavUl>
	</Navbar>
</header>

<main>
	<slot />
</main>

<Footer footerType="socialmedia">
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
		font-family: "Poppins", sans-serif;
	}
</style>
