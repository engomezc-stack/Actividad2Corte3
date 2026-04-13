<script lang="ts">
	import type { Character } from '$lib/entities/character/types';

	export let characters: Character[] = [];
</script>

{#if characters.length === 0}
	<p
		class="mt-4 rounded-3xl border border-white/60 bg-white/62 px-6 py-5 text-[#61718a] shadow-[0_16px_30px_rgba(16,35,63,0.06)]"
	>
		No hay resultados para ese filtro.
	</p>
{:else}
	<div class="grid gap-[1.1rem] [grid-template-columns:repeat(auto-fit,minmax(240px,1fr))]">
		{#each characters as character}
			<article
				class="overflow-hidden rounded-[28px] border border-white/60 bg-[linear-gradient(180deg,rgba(255,255,255,0.9),rgba(255,255,255,0.74))] shadow-[0_20px_44px_rgba(16,35,63,0.1),inset_0_1px_0_rgba(255,255,255,0.82)] backdrop-blur-md transition duration-200 hover:-translate-y-1 hover:shadow-[0_24px_48px_rgba(16,35,63,0.14),inset_0_1px_0_rgba(255,255,255,0.86)]"
			>
				<img
					src={character.image}
					alt={character.name}
					loading="lazy"
					class="h-[220px] w-full object-cover sm:h-[240px]"
				/>

				<div class="p-[1.05rem] pb-[1.15rem]">
					<div class="flex items-start justify-between gap-3">
						<div>
							<h2 class="mb-1 text-[1.08rem] font-semibold tracking-[-0.02em] text-[#10233f]">
								{character.name}
							</h2>
							<p class="mb-4 text-[#64748c]">{character.status} · {character.species}</p>
						</div>

						<div
							class="mt-1 h-3.5 w-3.5 shrink-0 rounded-full bg-[linear-gradient(180deg,#6dd3ff,#3b82f6)] shadow-[0_0_0_6px_rgba(109,211,255,0.14)]"
						></div>
					</div>

					<dl class="grid gap-3">
						<div class="rounded-[18px] bg-[rgba(244,248,255,0.85)] px-3.5 py-3">
							<dt class="text-[0.74rem] uppercase tracking-[0.12em] text-[#7e8ea5]">Origen</dt>
							<dd class="mt-1 text-[#18314f]">{character.originName}</dd>
						</div>

						<div class="rounded-[18px] bg-[rgba(244,248,255,0.85)] px-3.5 py-3">
							<dt class="text-[0.74rem] uppercase tracking-[0.12em] text-[#7e8ea5]">
								Ubicaci&oacute;n
							</dt>
							<dd class="mt-1 text-[#18314f]">{character.locationName}</dd>
						</div>
					</dl>
				</div>
			</article>
		{/each}
	</div>
{/if}
