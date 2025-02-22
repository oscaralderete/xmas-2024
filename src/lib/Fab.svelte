<script>
	export let active, toggle;
</script>

<button
	class="boton {active ? 'active' : ''}"
	aria-label="button play"
	onclick={toggle}
>
	<div class="icono">
		<div class="parte izquierda"></div>
		<div class="parte derecha"></div>
	</div>
</button>
