<script>
	import Nav from '../components/Nav.svelte'
	export let segment;
	export let screenHeight
	import { sineOut } from "svelte/easing";
	import { fly } from 'svelte/transition';

	$: isIndex = segment == undefined ? true : false
</script>

<style>

</style>

<svelte:window bind:outerHeight={screenHeight} />

<div class="min-h-screen flex flex-col">

<div  class="w-full  z-100 flex flex-col" class:absolute="{isIndex == true}" class:bg-gray-900="{isIndex != true}">
						   
	
	<header>
		<div class="container container-sm mx-auto z-10">
			<Nav {segment} />
		</div>

		
	</header>
</div>


		{#key segment}
		<div class="flex flex-col flex-1"
			in:fly="{{ y: -50, duration: 250, delay: 300 }}"
			out:fly="{{ y: -50, duration: 250 }}" 
		>
			<main>
				<slot></slot>
			</main>
		</div>
		{/key}



	

	<footer class="w-full py-28 bg-cover bg-fixed relative flex flex-col" style="background-image: url('/stock_images/bg-3.jpg')">
		<div class="w-full h-full absolute top-0 left-0 bg-gray-900 opacity-95"></div>
		<div class="container container-md mx-auto">
			<div class="grid grid-cols-1 md:grid-cols-3 uppercase text-white font-semibold text-3xl relative gap-12">
				<div class="flex flex-col text-center">
					<span> <i class="fa fa-mobile-alt text-gray-300  text-white p-3"></i> Telefon </span>
					<a href="tel:05353632881" class="text-lg P-3 text-gray-300"> +90 ( 0535 ) 363 28 81 </a>
				</div>


				<div class="flex flex-col text-center">
					<span> <i class="fas fa-map-marker-alt text-white p-3"></i> Adres </span>
					<address class="text-lg P-3 text-gray-300">Şeyhsinan mahallesi eski sanayi çarşısı 1.sokak no:9/1 çorlu/tekirdağ</address>
				</div>




				<div class="flex flex-col text-center">
					<span> <i class="fa fa-envelope text-white p-3 "></i> E-posta </span>
					<a href="mailto:corluzirve@gmail.com" class="text-lg P-3 text-gray-300"> corluzirve@gmail.com </a>
				</div>
			</div>

			<div class="flex relative text-gray-300  justify-center pt-12">
				<a href="#facebook"><i class="fab fa-facebook-f fa-3x p-12"></i></a>
				<a href="#instagram"><i class="fab fa-instagram fa-3x p-12"></i></a>
				<a href="#twitter"> <i class="fab fa-twitter fa-3x p-12"></i></a>
			</div>

			<div class="flex relative text-md P-3 text-gray-300 font-semibold justify-center mt-12"><span>çorlu zirve asansör© 2018 tüm hakları saklıdır</span></div>
		</div>
	</footer>
</div>