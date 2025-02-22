<script>
	// @ts-nocheck
	import Fab from "./lib/Fab.svelte";
	import Main from "./lib/Main.svelte";
	import Message from "./lib/Message.svelte";

	function stopSequence() {
		sequence = 0;
		clearInterval(timeout);
		timeout = null;
	}

	// @ts-ignore
	function stopAudio() {
		// @ts-ignore
		audio.pause();

		// @ts-ignore
		audio.currentTime = 0;

		// confetti
		fireworks();
	}

	function closeMsg() {
		stopSequence();

		stopAudio();
	}

	function toggle() {
		active = !active;

		if (active) {
			sequence = 1;

			// @ts-ignore
			audio.play();
			audio.volume = 0.5;

			timeout = setInterval(() => {
				sequence = sequence + 1;
				if (sequence > 6) {
					closeMsg();

					active = false;
				}
			}, slide_time);
		} else {
			closeMsg();
		}
	}

	function fireworks() {
		// confetti js
		for (let i = 0; i < ranges.length; i++) {
			window.confetti(
				Object.assign({}, defaults, {
					particleCount,
					origin: {
						x: randomInRange(ranges[i][0], ranges[i][1]),
						y: Math.random() - 0.2,
					},
				}),
			);
		}
	}

	function randomInRange(min, max) {
		return Math.random() * (max - min) + min;
	}

	let active = false,
		sequence = 0,
		timeout = null,
		slide_time = 6000,
		audio = document.getElementById("audio"),
		duration = 15 * 1000,
		animationEnd = Date.now() + duration,
		defaults = { startVelocity: 30, spread: 360, ticks: 60, zIndex: 0 },
		particleCount = 250,
		ranges = [
			[0.1, 0.25],
			[0.3, 0.45],
			[0.55, 0.7],
			[0.75, 0.9],
		];
</script>

<Main />

<!-- play/exit -->
<Fab {active} {toggle} />

<Message {active} {sequence} />
