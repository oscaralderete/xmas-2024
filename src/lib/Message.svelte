<script>
	import Card from "./Card.svelte";

	export let active, sequence;
</script>

<section id="message" class={active ? "active" : ""}>
	{#if sequence == 1}
		<Card>
			<p>
				Hola emprededor o emprendedora,<br />
				en estas fiestas de fin de año<br />
				queremos desearte una Feliz Navidad,<br />
				Feliz Hanukkah o Feliz Kwanzaa.
			</p>
		</Card>
	{:else if sequence == 2}
		<Card>
			<p>
				Sea cual sea tu credo,<br />
				nos unimos con profundo respeto<br />
				a tu celebración de fé y esperanza.
			</p>
		</Card>
	{:else if sequence == 3}
		<Card>
			<p>
				Si este ha sido un año de éxitos<br />
				estamos seguros que la idea que<br />
				dió inicio a tu emprendimiento<br />
				ha demostrado que tenías la razón.
			</p>
		</Card>
	{:else if sequence == 4}
		<Card>
			<p>
				Si este ha sido un año difícil<br />
				no dejes de creer en ti mismo.
			</p>
		</Card>
	{:else if sequence == 5}
		<Card>
			<p>
				Muchos emprendedores que hoy<br />
				disfrutan del éxito te confirmarán<br />
				que su camino hacia el triunfo<br />
				estuvo pavimentado de fracasos.
			</p>
		</Card>
	{:else if sequence == 6}
		<Card>
			<p>
				Todo es cuestión de creer.<br />
				Creemos en ti y tus ideas porque<br />
				nuestro trabajo es hacerlas realidad.
			</p>
			<a href="https://wpe.oscaralderete.com" target="_blank"
				><img
					src="https://wpe.oscaralderete.com/felices-fiestas/img/wpe-logo.png"
					alt="logo de WPE"
				/></a
			>
			<p class="short">Agencia de Programación</p>
		</Card>
	{/if}
</section>
