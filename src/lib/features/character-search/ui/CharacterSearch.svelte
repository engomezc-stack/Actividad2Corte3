<script lang="ts">
	export let query: string = '';
	export let onQueryChange: (value: string) => void;
</script>

<label class="grid gap-3">
	<span class="text-[0.8rem] font-bold uppercase tracking-[0.12em] text-[#7285a1]">
		Buscar personaje
	</span>

	<div
		class="flex items-center gap-3 rounded-3xl border border-white/55 bg-white/78 px-4 shadow-[inset_0_1px_0_rgba(255,255,255,0.8),0_16px_34px_rgba(37,99,235,0.08)] backdrop-blur-md transition duration-200 focus-within:-translate-y-px focus-within:border-[rgba(109,211,255,0.7)] focus-within:shadow-[inset_0_1px_0_rgba(255,255,255,0.84),0_20px_36px_rgba(37,99,235,0.12),0_0_0_5px_rgba(109,211,255,0.12)]"
	>
		<div
			aria-hidden="true"
			class="flex h-10 w-10 shrink-0 items-center justify-center rounded-[18px] bg-[linear-gradient(180deg,rgba(59,130,246,0.12),rgba(37,99,235,0.04))] text-[#3f6db1]"
		>
			<svg viewBox="0 0 24 24" focusable="false" class="h-[1.15rem] w-[1.15rem] fill-current">
				<path
					d="M10.5 4.75a5.75 5.75 0 1 0 0 11.5a5.75 5.75 0 0 0 0-11.5Zm0-1.5a7.25 7.25 0 1 1 0 14.5a7.25 7.25 0 0 1 0-14.5Zm6.04 12.23l4 4a.75.75 0 1 1-1.06 1.06l-4-4a.75.75 0 0 1 1.06-1.06Z"
				/>
			</svg>
		</div>

		<input
			type="search"
			placeholder="Rick, Morty, Summer..."
			value={query}
			class="w-full border-0 bg-transparent py-4 pr-0.5 text-[0.98rem] text-[#10233f] outline-none placeholder:text-[#8a98ab]"
			on:input={(event) => onQueryChange((event.currentTarget as HTMLInputElement).value)}
		/>
	</div>
</label>
