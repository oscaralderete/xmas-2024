<script>
	import ProgressBar from "./ProgressBar.svelte";

	const slide_time = 6,
		frecuency = 0.5; // by 1 second;
	let width = $state(0);

	$effect(() => {
		const ratio = 100 / (slide_time / frecuency);
		let interval = null;
		interval = setInterval(() => {
			width += ratio;
		}, 1000 * frecuency);

		return () => {
			clearInterval(interval);
		};
	});
</script>

<ProgressBar {width} />

<!-- svelte-ignore slot_element_deprecated -->
<slot />
