<script>
	import { RangeCalendar as RangeCalendarPrimitive } from 'bits-ui';
	import { Icon } from '@steeze-ui/svelte-icon';
	import { ChevronRight } from '@steeze-ui/radix-icons';
	import { buttonVariants } from '$lib/atoms/shadcn/button';
	import { cn } from '$lib/utils';

	/** @type {string | undefined | null} */
	let className = undefined;

	export { className as class };
</script>

<RangeCalendarPrimitive.NextButton
	on:click
	class={cn(
		buttonVariants({ variant: 'ghost' }),
		'h-7 w-7 bg-transparent p-0 opacity-50 hover:opacity-100',
		className
	)}
	{...$$restProps}
	let:builder
>
	<slot {builder}>
		<Icon src={ChevronRight} class="h-4 w-4" />
	</slot>
</RangeCalendarPrimitive.NextButton>
