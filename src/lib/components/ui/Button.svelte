<script>
	/**
	 * Button component with multiple variants
	 * @type {'primary' | 'secondary'}
	 */
	export let variant = 'primary';

	/**
	 * Button size
	 * @type {'sm' | 'md' | 'lg'}
	 */
	export let size = 'md';

	/**
	 * Disabled state
	 */
	export let disabled = false;

	/**
	 * Button type
	 * @type {'button' | 'submit' | 'reset'}
	 */
	export let type = 'button';

	/**
	 * Additional CSS classes
	 */
	let className = '';
	export { className as class };

	// CSS classes based on variant and size
	$: buttonClasses = [
		'font-gt-america-mono inline-flex items-center justify-center font-medium transition-all duration-200 uppercase cursor-pointer',
		'focus:text-dark focus:bg-primary focus:border-primary',
		'disabled:opacity-50 disabled:cursor-not-allowed',

		// Variant styles
		variant === 'primary' &&
			'bg-transparent border-2 border-white text-white rounded-full hover:text-primary hover:border-primary ',
		variant === 'secondary' &&
			'bg-primary text-dark aspect-square p-6 md:p-8 rounded-full hover:bg-white',
		variant === 'gsd' &&
			'bg-transparent text-white font-sf-pro-display w-full !justify-between border-b-2 !px-0 py-3 border-white !normal-case text-xl group',

		// Size styles
		size === 'md' && 'px-7 py-3 text-base',
		size === 'lg' && 'w-[150px] py-3 text-base',

		// Active state styling (overrides variant styles)
		className?.includes('active') && '!bg-primary !text-dark !border-primary',

		// Custom classes
		className
	]
		.filter(Boolean)
		.join(' ');

	// Dynamic style for small size
	$: buttonStyle = size === 'sm' ? 'font-size: var(--font-size-fluid-xs);' : '';

	// Filter out problematic ARIA attributes
	$: filteredProps = Object.fromEntries(
		Object.entries($$restProps).filter(([key]) => 
			!['role', 'aria-selected', 'aria-controls'].includes(key)
		)
	);
</script>

<button class={buttonClasses} style={buttonStyle} {type} {disabled} on:click {...filteredProps}>
	<slot />
	{#if variant === 'gsd'}
		<svg
			viewBox="0 0 12 12"
			class="h-[12px] w-[12px] transition-all duration-200 group-hover:-rotate-90"
		>
			<path
				d="M1,1l10,10"
				fill="none"
				stroke="#fff"
				stroke-linecap="round"
				stroke-linejoin="round"
				stroke-width="1.5"
			/>
			<path
				d="M11,1v10H1"
				fill="none"
				stroke="#fff"
				stroke-linecap="round"
				stroke-linejoin="round"
				stroke-width="1.5"
			/>
		</svg>
	{/if}
</button>
