<script>
	import { Navbar, NavBrand, NavLi, NavUl, NavHamburger } from 'flowbite-svelte';
	import {
		FacebookSolid,
		InstagramSolid,
		TwitterSolid,
		MapPinAltSolid,
		EnvelopeSolid,
		PhoneSolid,
		CaretRightSolid
	} from 'flowbite-svelte-icons';
	import { Button } from 'flowbite-svelte';
	import StickyContent from './Navbar_banner/StickyContent.svelte';
	import SeparatorSection from '../routes/separator/separatorSection.svelte';
	import Carousel from 'svelte-carousel';
	import { browser } from '$app/environment';

	let carousel;

	const handleNextClick = () => {
		carousel.goToNext();
	};

	let stickToTop = true;
</script>

<svelte:head>
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
	<link
		href="https://fonts.googleapis.com/css2?family=Dosis:wght@200..800&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<!-- BARRA DE INFORMACION -->
<Navbar let:NavContainer color="primary">
	<NavContainer class=" flex items-center justify-between gap-5 rounded-lg bg-white px-5 py-2">
		<section class="section-social-networks ml-[5%] flex items-start justify-center gap-[2rem]">
			<NavBrand href="">
				<FacebookSolid class="dark:text-white" />
			</NavBrand>
			<NavBrand href="">
				<InstagramSolid class="dark:text-white" />
			</NavBrand>
			<NavBrand href="">
				<TwitterSolid class="dark:text-white" />
			</NavBrand>
		</section>
		<NavHamburger menuClass="h-5 w-5 shrink-0" />
		<NavUl class="mr-[5%]" slideParams="delay: 150, duration: 500, easing: sineIn">
			<NavLi href="/" class="mr-5 flex items-center justify-center">
				<MapPinAltSolid class="mr-2 dark:text-white" />
				<span class="text-sm dark:text-white">Av. Pedro Venturo 104, Surco</span>
			</NavLi>
			<NavLi href="/" class="mr-5 flex items-center justify-center">
				<EnvelopeSolid class="mr-2 dark:text-white" />
				<span class="text-sm dark:text-white">rondon@veterinariarondon.com</span>
			</NavLi>
			<NavLi href="/" class="mr-5 flex items-center justify-center">
				<PhoneSolid class="mr-2 dark:text-white" />
				<span class="text-sm dark:text-white">208 4900</span>
			</NavLi>
		</NavUl>
	</NavContainer>
</Navbar>

<main>
	<div class="body">
		<StickyContent {stickToTop}>
			<section class="section-banner">
				<div class="text-banner m-4 w-full">
					<span class="conteiner-text-banner text-[5rem] text-[white]">
						URGENCIAS LAS 24 HORAS
					</span>
					<span class="conteiner-text-banner text-[1.3rem] text-[white] overline">
						CONSULTAS MEDICAS, VACUNAS, DESPARACITACION, EXAMENES DE LABORATORIOS, DERMATOLOGIA,
						INTERCONSULTA Y TRAUMATOLOGIA
					</span>
					<Button href="/" class="m-3 flex items-center justify-center bg-orange-600">
						<span class="m-3 mr-1 text-[1.5rem]">Contactanos</span>
						<CaretRightSolid class="h-[2rem] w-[2rem]" />
					</Button>
				</div>
			</section>
			<SeparatorSection />
			<section id="QuienesSomos" class="Quienes-Somos">
				<div class="contenedorTexto-Quienes-Somos">
					<span class="flex flex-col text-[3rem] text-[#706F6F]"
						>¿Quienes Somos?
						<hr class="separator-texto-quienSomos mb-4 mt-4" />
					</span>

					<span class="mx-[20%] text-[#706F6F]"
						>Cuando se trata de expresar la belleza de la vida y del mundo que nos rodea, a travEs
						del lenguaje escrito, la poesía cuenta con una posiciOn privilegiada. Es una de las
						formas literarias mAs cargada de emociones, e identificar un texto de connotacin poica
						es bastante sencillo, solo basta con adentrase un poco en sus líneas. Existen algunas
						herramientas bsicas utilizadas por los poetas, que se pueden apreciar de manera
						automtica, aunque no se tenga una amplia experiencia como lector de poesía. Lagrima, por
						ejemplo, es una de las tcnicas que son apreciables por la sonoridad que aportan a los
						textos y por la forma en que se graban en la mente.Dichos mtodos literarios se pueden
						dejar de lado, segn el tipo de escritor, hay una característica singular, que
						independientemente de la forma y el estilo del autor, no queda de lado. Y esa es la
						belleza misma de las líneas, ya que, aunque los poemas hablen de las situaciones ms
						oscuras de la vida, encierran una belleza intrínseca f cilmente apreciable.</span
					>
				</div>
				<div class="contenedor-carousel flex h-full w-full items-center justify-center relative z-0">
					<div class="carousel flex h-[30rem] w-full items-center justify-center pr-8">
						{#if browser}
							<Carousel
								autoplay
								autoplayDuration={3000}
								autoplayProgressVisible
								bind:this={carousel}
							>
								<div class="imagenes-carousel flex justify-center items-center">
									<img
										id="slide-1"
										src="https://res.cloudinary.com/dfjn83ofc/image/upload/v1720908390/WhatsApp_Image_2024-07-13_at_4.40.31_PM_wmshq8.jpg"
										alt="gato1"
									/>
								</div>
								<div class="imagenes-carousel flex justify-center items-center">
									<img
										id="slide-2"
										src="https://res.cloudinary.com/dfjn83ofc/image/upload/v1720908412/WhatsApp_Image_2024-07-13_at_4.40.31_PM_1_ia6yxz.jpg"
										alt="gato2"
									/>
								</div>
								<div class="imagenes-carousel flex justify-center items-center">
									<img
										id="slide-3"
										src="https://res.cloudinary.com/dfjn83ofc/image/upload/v1720839963/gate_er0fzz.png"
										alt="gato3"
									/>
								</div>
							</Carousel>
						{/if}
					</div>
				</div>
			</section>
			<SeparatorSection />
			<section id="NuestraFamilia" class="Nuestra-Familia">
				<div class="contenedorTitulo-Nuestra-Familia m-[4rem] flex justify-center">
					<span class="flex flex-col text-[3rem] text-[#706F6F]"
						>Nuestra Familia
						<hr class="separator-texto-quienSomos mb-4 mt-4" />
					</span>
				</div>
                <div class="ContenedorFotoTexto">
                    <div></div>
                    <div></div>
                    <div></div>
                </div>
			</section>
		</StickyContent>
	</div>
</main>

<style>
	.body {
		background-image: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
			url('https://res.cloudinary.com/dfjn83ofc/image/upload/v1720748531/banner_wu4f6o.png');
		background-size: cover;
		background-repeat: no-repeat;
		background-position: center center;
		background-attachment: fixed;
		width: 100%;
		height: 80vh;
	}
	.text-banner {
		height: 60vh;
		width: 99%;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}
	.conteiner-text-banner {
		line-height: 3.5rem;
	}
	.Quienes-Somos {
		background-color: #f9f9f9;
		display: grid;
		grid-template-columns: 50% 50%;
		width: 100%;
		padding-top: 3%;
		padding-bottom: 3%;
		height: auto;
	}
	.contenedorTexto-Quienes-Somos {
		flex-direction: column;
		margin: 1rem;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.separator-texto-quienSomos {
		border: 2px solid #f2b861;
		width: 100%;
	}
	span {
		line-height: 1.7rem;
	}
	.imagenes-carousel img {
		object-fit: contain;
		transition: transform 0.5s ease;
        height: 50vh;
        width: 100%;
	}
</style>
