<script>
	import {
		Button,
		Alert,
		Card,
		Navbar,
		NavBrand,
		NavLi,
		NavUl,
		NavHamburger,
		Toast
	} from 'flowbite-svelte';
	import { FireOutline } from 'flowbite-svelte-icons';
</script>

<Button color="primary">Primary</Button>
<Alert color="primary">Primary</Alert>
<Card href="/cards" color="primary">
	<h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-red-800">
		Noteworthy technology acquisitions 2021
	</h5>
	<p class="font-normal leading-tight text-gray-700 dark:text-gray-700">
		Here are the biggest enterprise technology acquisitions of 2021 so far, in reverse chronological
		order.
	</p>
</Card>
<Navbar let:hidden let:toggle color="primary">
	<NavBrand href="/">
		<span class="self-center whitespace-nowrap text-xl font-semibold dark:text-red-800"
			>Flowbite</span
		>
	</NavBrand>
	<NavHamburger on:click={toggle} />
	<NavUl {hidden}>
		<NavLi href="/about">About</NavLi>
		<NavLi href="/services">Services</NavLi>
		<NavLi href="/pricing">Pricing</NavLi>
		<NavLi href="/contact">Contact</NavLi>
	</NavUl>
</Navbar>
<Toast color="primary">
	<svelte:fragment slot="icon">
		<FireOutline class="h-6 w-6" />
	</svelte:fragment>
	Dismissable user notification.
</Toast>
