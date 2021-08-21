<script>
	import Footer from './components/Footer.svelte';
	import Header from "./components/header.svelte";
	import Tabs from "./shared/Tabs.svelte";

	//tabs
	let items = ['نظرسنجی های فعلی','افزودن نظرسنجی جدید']
	let activeItem = 'نظرسنجی های فعلی';
	const tabChange = (e) => {
		activeItem = e.detail;
	}
</script>
<Header />
<main>
	<Tabs {activeItem} {items} on:tabChange={tabChange}/>
	{#if activeItem === 'نظرسنجی های فعلی'}
		<p>نظرسنجی فعلی</p>
	{:else if activeItem == 'افزودن نظرسنجی جدید'}
		<p>نظرسنجی جدید</p>
	{/if}
</main>
<Footer/>
<style>
	main{
		max-width: 960px;
		margin: 40px auto;
	}
</style>