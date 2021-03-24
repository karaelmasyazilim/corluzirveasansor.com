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
			
			<a href="/" class="z-10 w-66">
				<img src="/logo.png" class="w-66" alt="">
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
	<main>
		<slot></slot>
	</main>
</div>


