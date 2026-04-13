<script lang="ts">
	import '../app.css';
</script>

<svelte:head>
	<title>Prueba Lectiva</title>
	<meta
		name="description"
		content="Base SvelteKit con arquitectura feature-first/domain-first para integrar Rick and Morty."
	/>
</svelte:head>

<div class="relative min-h-screen overflow-x-hidden">
	<div
		class="pointer-events-none fixed left-[-4rem] top-20 h-56 w-56 rounded-full bg-[rgba(123,156,245,0.18)] blur-3xl"
	></div>
	<div
		class="pointer-events-none fixed right-[-3rem] top-80 h-44 w-44 rounded-full bg-[rgba(109,211,255,0.16)] blur-3xl"
	></div>

	<slot />
</div>
