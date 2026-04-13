<script lang="ts">
	import { CharacterList } from '$lib/features/character-list';
	import { CharacterSearch } from '$lib/features/character-search';
	import type { CharacterBrowserData } from '../model';

	export let data: CharacterBrowserData;
	export let onQueryChange: (value: string) => void;
</script>

<div class="mx-auto max-w-[1080px] px-4 pb-14 pt-8 sm:px-5">
	<section class="mx-auto max-w-[960px] px-2 pb-6 pt-6 sm:pt-11">
		<div
			class="inline-flex items-center gap-1 rounded-full border border-white/50 bg-white/55 px-4 py-2 text-[0.78rem] font-bold uppercase tracking-[0.12em] text-[#46617f] shadow-[0_10px_30px_rgba(37,99,235,0.08)] backdrop-blur-md"
		>
			SvelteKit · Rick and Morty
		</div>

		<h1
			class="mt-4 max-w-[12ch] text-[clamp(2.7rem,7vw,5rem)] font-semibold leading-[0.92] tracking-[-0.04em] text-[#10233f]"
		>
			Explora personajes con una interfaz m&aacute;s clara y premium.
		</h1>

		<p class="mt-4 max-w-[60ch] text-[1.03rem] leading-7 text-[#5f6f86]">
			Base feature-first/domain-first con contratos claros entre pantalla, dominio y API.
		</p>
	</section>

	<div
		class="mx-auto grid max-w-[960px] gap-[1.15rem] rounded-[32px] border border-white/55 bg-[linear-gradient(180deg,rgba(255,255,255,0.82),rgba(255,255,255,0.68))] p-4 shadow-[0_24px_60px_rgba(16,35,63,0.12),inset_0_1px_0_rgba(255,255,255,0.75)] backdrop-blur-[22px] sm:p-[1.4rem]"
	>
		<div class="flex flex-wrap items-center justify-between gap-4">
			<div>
				<p class="mb-1.5 text-[0.75rem] font-bold uppercase tracking-[0.14em] text-[#6e83a0]">
					B&uacute;squeda en tiempo real
				</p>
				<h2 class="text-[1.55rem] font-semibold tracking-[-0.03em] text-[#10233f]">
					Directorio gal&aacute;ctico
				</h2>
			</div>

			<div
				class="inline-flex min-h-11 items-center justify-center rounded-full border border-white/60 bg-white/70 px-4 py-2 text-[0.92rem] font-bold text-[#34506f] shadow-[0_10px_25px_rgba(148,163,184,0.15)]"
			>
				{data.total} personajes
			</div>
		</div>

		<CharacterSearch query={data.query} onQueryChange={onQueryChange} />

		<div class="flex flex-wrap items-center justify-between gap-4">
			<p class="m-0 text-[0.95rem] text-[#6a7b92]">
				Resultados sincronizados con la API de Rick and Morty.
			</p>

			{#if data.error}
				<p
					class="m-0 rounded-2xl bg-[rgba(255,237,237,0.85)] px-4 py-3 text-sm font-semibold text-[#c94848]"
				>
					{data.error}
				</p>
			{/if}
		</div>

		<CharacterList characters={data.characters} />
	</div>
</div>
