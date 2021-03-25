<script>
	import Nav from '../components/Nav.svelte'
	export let segment;
	let screenHeight;
	function handleScroll() {
		//$scrollTo = screenHeight
		if(window) {

			window.scrollTo(0,screenHeight)
		}
	}
</script>

<style>
</style>
<svelte:window bind:outerHeight={screenHeight} />


<div  class="w-full h-screen relative">
	
	<header class="w-full h-screen flex flex-col bg-cover bg-fixed"  style="background-image: url('/stock_images/asansor.jpg');">
		<div class="top-0 left-0 w-full h-screen  absolute bg-gray-800 bg-opacity-40 z-0"></div>
		<div class="container container-sm mx-auto z-10">
			<Nav {segment} />
		</div>

		<div class="flex flex-col flex-1 justify-center mb-40 items-center z-10">
			
			<a href="/" class="z-10 w-66 hidden sm:block">
				<img src="/logo.png" class="w-66 " alt="">
			</a>
			<h1 class="text-white text-7xl font-extrabold p-4 uppercase text-center">zirve asansör </h1>
			<div class="z-10 w-5/10 sm:w-2/10 md:-3/10 mb-6">
				<hr class="border-t-3 mb-1 border-red-500" />
				<hr class="border-t-3 border-red-500" />
				
			</div>
			<button class="flex w-12 h-12 border-4 rounded-full border-white outline-none items-center justify-center" on:click={handleScroll}>
				<i class="fa fa-chevron-down fa-2x text-white"></i>
			</button>
		</div>
	</header>
</div>



	<main>
		<slot></slot>
	</main>

	<div class="w-full h-156">
		<iframe title="map" src="https://www.google.com/maps/embed?pb=!1m10!1m8!1m3!1d24034.00816978646!2d27.7885961!3d41.1508736!3m2!1i1024!2i768!4f13.1!5e0!3m2!1str!2str!4v1539594890165"
		 frameborder="0" width="100%" height="100%" style="border:0" allowfullscreen=""></iframe>
	</div>


	<footer class="w-full py-28 bg-cover bg-fixed relative" style="background-image: url('/stock_images/bg-3.jpg')">
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
