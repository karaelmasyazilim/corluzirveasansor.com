


<script>

	import { fade } from 'svelte/transition';
	import  { quintInOut } from 'svelte/easing'
	import { goto } from '@sapper/app'
	import { tweened } from 'svelte/motion';
	import {onMount} from 'svelte'


	export let screenHeight;
	function handleScroll() {
		//$scrollTo = screenHeight
		if(window) {

			window.scrollTo(0,screenHeight)
		}
	}
    let portfoy = [
		{
			img: '/stock_images/elevator3.jpg',
			workName: 'Çalışma adı 1',
			workText: 'Yüksek malzeme kalitesi, Tecrübeli ustalarımız sayesinde uzun yıllar sorunsuz kullanılabilecek asansörler'
		},
		{
			img: '/stock_images/elevator3.jpg',
			workName: 'Çalışma adı 2',
			workText: 'Yüksek malzeme kalitesi, Tecrübeli ustalarımız sayesinde uzun yıllar sorunsuz kullanılabilecek asansörler'
		},
		{
			img: '/stock_images/elevator3.jpg',
			workName: 'Çalışma adı 3',
			workText: 'Yüksek malzeme kalitesi, Tecrübeli ustalarımız sayesinde uzun yıllar sorunsuz kullanılabilecek asansörler'
		},
		{
			img: '/stock_images/elevator3.jpg',
			workName: 'Çalışma adı',
			workText: 'Yüksek malzeme kalitesi, Tecrübeli ustalarımız sayesinde uzun yıllar sorunsuz kullanılabilecek asansörler'
		},
		{
			img: '/stock_images/elevator3.jpg',
			workName: 'Çalışma adı',
			workText: 'Yüksek malzeme kalitesi, Tecrübeli ustalarımız sayesinde uzun yıllar sorunsuz kullanılabilecek asansörler'
		},
		{
			img: '/stock_images/elevator3.jpg',
			workName: 'Çalışma adı',
			workText: 'Yüksek malzeme kalitesi, Tecrübeli ustalarımız sayesinde uzun yıllar sorunsuz kullanılabilecek asansörler'
		},
		
	]
	let slider = [
		{
			img: '/stock_images/asansor.jpg',
			header : 'Ürün adı1',
			text : `Lorem Ipsum, dizgi ve basIpsum sürümleri içeren masaüstü yayıncılık yazılımları ile popüler olmuştur.`,
			btnText : 'daha fazla bilgi',
			btnLink : '#link'
		},
		{
			img: '/stock_images/asansor2.jpg',
			header : 'Ürün adı2',
			text : `kı endüstrisinde kullanılan mıgır metinlerdir. Lorem Ipsum, adı bilinmeyen bir matbaacının bir hurufat numune kitabı oluşturmak üzere bir yazı galerisini alarak karıştırdığı 1500'lerden beri endüstri standardı sahte metinler olarak kullanılmıştır. Beşyüz yıl boyunca varlığını sürdürmekle kalmamış, aynı zamanda pek değişmeden elektronik dizgiye de sıçramıştır. 1960'larda Lorem Ipsum pasajları da içeren Letraset yapraklarının yayınlanması ile 
			ve yakın zamanda Aldus PageMaker gibi Lorem Ipsum sürümleri içeren masaüstü yayıncılık yazılımları ile popüler olmuştur.`,
			btnText : 'daha fazla bilgi',
			btnLink : '#link'
		},
		{
			img: '/stock_images/asansor3.png',
			header : 'Ürün adı3',
			text : `PageMaker gibi Lorem Ipsum sürümleri içeren masaüstü yayıncılık yazılımları ile popüler olmuştur.`,
			btnText : 'daha fazla bilgi',
			btnLink : '#link'
		},
	]

	let sliderMax = slider.length - 1
	let currentSlide = 0
	let sliderInterval
	function sliderIntervalFunc() {
		handleSliderMoveRight()
	}

	function pauseSlider() {
		clearInterval(sliderInterval)
	}

	function resumeSlider() {
		sliderInterval = setInterval(sliderIntervalFunc, 5000)
	}
    onMount(async () => {
		(function() {
			sliderInterval = setInterval(sliderIntervalFunc, 5000)
		})()
	})

	function handleSlideBtnClick(link) {
		goto('#slide')
	}	

	function handleSliderMoveLeft() {
		if(currentSlide <= 0) {
			currentSlide = sliderMax 
		} else currentSlide--
		 
	}

	function handleSliderMoveRight() {
		if(currentSlide == sliderMax) currentSlide = 0
		else currentSlide++
	}

	let portfoyOnView

	function handlePortfoy(work, id) {
		portfoyOnView = {work, id}
		portfoy.splice(id, 1, {})
		portfoy = portfoy
	}

	function handlePortfoyClose() {
		portfoy.splice( portfoyOnView.id, 1,portfoyOnView.work );
		portfoy = portfoy
		portfoyOnView = undefined
	}
</script>

<svelte:window bind:outerHeight={screenHeight} />

<div  class="w-full h-screen flex flex-col bg-cover bg-fixed z-0 relative pt-24"  style="background-image: url('/stock_images/asansor.jpg');">
	
	<div class="top-0 left-0 w-full h-screen  absolute bg-gray-900 bg-opacity-70 z-0"></div>
	<div class="flex flex-col flex-1 justify-center mt-24 items-center z-10">
		
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
</div>

<div class="container container-sm mx-auto bg-white">
	<div class="flex flex-col py-42">
		<h2 class="text-5xl font-extrabold text-center">Müşteri Memnuniyeti</h2>
		<p class="text-4xl font-bold px-12 text-center py-6">
			Hizmet verdiğimiz her müşterimizi memnun etmeyi amaç edinmiş, kaliteden ödün vermeyi mazeret kabul etmeyen bir kuruluşuz
		</p>


		<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4  gap-12 pt-42">
			<div class="flex flex-col items-center ">
				<i class="fas fa-feather-alt fa-10x p-2 "></i>
				<h2 class="text-4xl p-6 font-semibold ">Güvenli</h2>
				<p class=" text-center font-semibold text-gray-900">
					EN 81 Standartlarına göre üretilmiş ürünlerin montajını bakımını ve takibini gerçekleştiriyoruz
				</p>
			</div>
			<div  class="flex flex-col items-center ">
				<i class="fab fa-accessible-icon fa-10x p-2 "></i>
				<h2 class="text-4xl p-6 font-semibold ">Erişilebilirlik</h2>
				<p class=" text-center font-semibold text-gray-900">
					Butün kabinlerimizde sesli işikli geri bildirim, Kabartmalı tuş takımları bulunmaktadır
				</p>
			</div>
			<div  class="flex flex-col items-center ">
				<i class="fas fa-archway fa-10x p-2 "></i>
				<h2 class="text-4xl p-6 font-semibold ">Zarif</h2>
				<p class=" text-center font-semibold text-gray-900">
					Yapınızla bir bütünmüş gibi görünen kapılar. Kullanıcılarına premium kalite malzeme deneyimi yaşatacaktır
				</p>
			</div>
			<div  class="flex flex-col items-center ">
				<i class="fa fa-cog fa-10x " aria-hidden="true"></i>
				<h2 class="text-4xl p-6 font-semibold ">Uzun ömürlü</h2>
				<p class=" text-center font-semibold text-gray-900">
					Yüksek malzeme kalitesi, Tecrübeli ustalarımız sayesinde uzun yıllar sorunsuz kullanılabilecek asansörler
				</p>
			</div>
		</div>


		<div class="pt-42">
			<h2 class="text-5xl font-extrabold text-center mb-6">Kadromuz</h2>
			<h3 class="text-3xl font-semibold text-center text-gray-900">İşini aşkla yapan ekibimiz</h3>
			<hr class="border-0 border-b-1 p-3 border-red-500">
			<div class="grid sm:grid-cols-3 grid-cols-1  gap-12 py-12">
				<div class="cardEmploye" style="background-image: url('/employe/user1.jpg')">
					<div class="employe-cover"></div>
					<h3>Taner Fırat</h3>
					<hr>
					<h4>Yönetici</h4>
					<div class="flex z-10 employe-social">
						
						<a href=""><i class="fab fa-facebook-square fa-3x p-2"></i></a>
						<a href=""><i class="fab fa-instagram-square fa-3x p-2"></i></a>
						<a href=""><i class="fab fa-google fa-3x p-2" aria-hidden="true"></i></a>
					</div>
				</div>
				<div class="cardEmploye" style="background-image: url('/employe/user2.jpg')">
					<div class="employe-cover"></div>
					<h3>Taner Fırat</h3>
					<hr>
					<h4>Yönetici</h4>
					<div class="flex z-10 employe-social">
						
						<a href=""><i class="fab fa-facebook-square fa-3x p-2"></i></a>
						<a href=""><i class="fab fa-instagram-square fa-3x p-2"></i></a>
						<a href=""><i class="fab fa-google fa-3x p-2" aria-hidden="true"></i></a>
					</div>
				</div>
				
				<div class="cardEmploye" style="background-image: url('/employe/user3.jpg')">
					<div class="employe-cover"></div>
					<h3>Taner Fırat</h3>
					<hr>
					<h4>Yönetici</h4>
					<div class="flex z-10 employe-social">
						
						<a href="" ><i class="fab fa-facebook-square fa-3x p-2"></i></a>
						<a href=""><i class="fab fa-instagram-square fa-3x p-2"></i></a>
						<a href=""><i class="fab fa-google fa-3x p-2"></i></a>
					</div>
				</div>
			</div>
		</div>



	</div>
</div>



<div class="w-full min-h-screen bg-fixed bg-cover relative flex flex-col items-center justify-center align-middle" style="background-image: url('/stock_images/bg-2.jpg')">
<div class="w-full h-full absolute top-0 left-0 opacity-30 bg-gray-600 z-0"></div>
<div class="z-10">
 <div class="container container-sm mx-auto text-white text-center flex flex-col align-middle items-center">
	<h3 class="text-4xl font-bold "><span class="text-4xl font-bold text-red-500 inline-block">Kaliteyi</span> iyi işçilik, titiz çalışma, kaliteli malzeme, güzel tasarım ve fonksiyonelliğin mükemmel uyumu ile <span class="text-red-500">sağlıyoruz</span></h3>
	<hr class="border-t-2 border-b-2 pb-1 mt-3 border-red-500 w-1/3">
		<button class="border-4 px-8 py-4 m-3 font-bold border-white rounded outline-none">Daha fazla bilgi</button>
 </div>
</div>
</div>


<div class="w-full bg-white py-22">
	<div class="container container-md mx-auto">
		<div class="w-full flex flex-col">
			<h2 class="text-5xl font-extrabold text-center mb-6 mt-12">Hizmetler</h2>
			<h3 class="text-3xl font-semibold text-center">Bir işi nasıl yaptığımızın özeti</h3>
			<hr class="border-0 border-b-1 p-3 border-red-500">
			<div class="grid grid-cols-1  md:grid-cols-3 gap-12">
				<div class="flex pt-6  justify-center"> 
				    <div><span class="inline-block p-6 border-4 border-gray-900 rounded-full"><i class="fas fa-drafting-compass fa-2x"></i></span> </div>
				
					<ul class="flex flex-col w-64">
						
						<li><h4 class="inline-block pl-8 font-extrabold text-2xl text-gray-900">Plan</h4></li>
						<li class="inline-block pl-8 font-semibold text-md ">Tespit</li>
						<li class="inline-block  pl-8 font-semibold font-bold text-md">Hazırlık</li>
						<li class="inline-block  pl-8 font-semibold  font-bold text-md">Projelendirme</li>
					</ul>
				</div>
				<div  class="flex pt-6 justify-center">
					<div><span class="block p-6 border-4 border-gray-900 rounded-full"> <i class="fas fa-money-bill fa-2x"></i> </span></div>
					
					<ul class="flex flex-col  w-64">
						<li><h4 class="pl-8 font-bold text-2xl text-gray-900">Satış & Montaj</h4></li>
						<li class="inline-block pl-8 font-semibold text-md">Tedarik</li>
						<li  class="inline-block pl-8 font-semibold text-md">Montaj</li>
						<li  class="inline-block pl-8 font-semibold text-md">Test</li>
					</ul>
				</div>
				<div  class="flex pt-6 justify-center">
					<div><span class="block p-6 border-4 border-gray-900 rounded-full"><i class="fab fa-whmcs fa-2x"></i>  </span></div>
					
					<ul class="flex flex-col  w-64">
						<li><h4 class="pl-8 font-bold text-2xl text-gray-900">Teknik destek</h4></li>
						<li class="inline-block pl-8 font-semibold text-md">Periyodik Bakımlar</li>
						<li  class="inline-block pl-8 font-semibold text-md">Arıza & Onarım</li>
						<li  class="inline-block pl-8 font-semibold text-md">Yedek Parça</li>
					</ul>
				</div>
			</div>
		</div>
	</div>
</div>


<div id="carousel" class="w-full min-h-screen flex items-center relative z-0" style="background-image: url('{slider[currentSlide] && slider[currentSlide].img || ''}');"
transition:fade
on:mouseenter={pauseSlider}
on:mouseleave={resumeSlider}
>
	<div id="carousel-cover" class="w-full h-full absolute duration-1000 top-0 left-0 z-0 "></div>
	<div class="flex relative z-10 w-full h-full items-center text-center">
		
		<!--Slider btn left-->
		<div class=" w-16 h-16 flex align-middle items-center bg-gray-700 cursor-pointer hover:bg-gray-900 duration-500"
			on:click={handleSliderMoveLeft}
		>
				<span class="w-full text-gray-300 hover:text-gray-400"><i class="fa fa-chevron-left fa-2x"></i></span>
		</div>

		<div class="flex-1">
			<div class="container container-md mx-auto text-white">
				
			<h2  transition:fade class="text-5xl font-extrabold text-center mb-6 mt-12 text-white">{slider[currentSlide] && slider[currentSlide].header || ''}</h2>
			<p 	 transition:fade class=" font-semibold text-lg">Lorem Ipsum, dizgi ve baskı endüstrisinde kullanılan mıgır metinlerdir. 
				 {slider[currentSlide] && slider[currentSlide].text}</p>
				 <button class="border-4 px-8 py-4 m-3 font-bold border-white rounded outline-none rounded" 
				 transition:fade
				 on:click={()=>handleSlideBtnClick(slider[currentSlide] && slider[currentSlide].btnLink || '' )}>{slider[currentSlide] && slider[currentSlide].btnText || ''}</button>
			</div>
		</div>


		<div class=" w-16 h-16 flex align-middle items-center bg-gray-700 cursor-pointer hover:bg-gray-900 duration-500"
		on:click={handleSliderMoveRight}
		>
		
			<span class="w-full text-gray-300 hover:text-gray-400"><i class="fa fa-chevron-right fa-2x"></i></span>
	
	</div>
	</div>
</div>

<div class="flex w-full min-h-screen bg-white z-10 relative">
   <div class="container container-md mx-auto">
	    <div class="w-full h-full flex flex-col items-center  justify-center ">
			<h2 class="text-5xl font-extrabold text-center mt-12 sm:mt-0 text-gray-900">PORTFÖY</h2>
			<h3 class="text-3xl font-semibold text-center my-6">Yapmış oldugumuz bazı çalışmalara göz atabilirsiniz</h3>
			<hr class="border-t-2 mt-3 mb-12 border-red-500 w-full">
			<div class="w-full  grid grid-cols-1 sm:grid-cols-3">

				{#each portfoy as work, id}
					
			
				<div class="w-full h-72  p-6 hover:p-0 hover:cursor-pointer duration-1000 relative z-0" on:click={()=>handlePortfoy(work, id)}>
					<div class="inner-portfoy w-full h-full bg-cover relative" style=" { work.img  ? 'background-image: url(' + work.img +');' : ''}">
						<div  class="portfoy-cover">
							<h3 class="text-2xl text-white font-extrabold w-full text-center p-6">{work.workName || ''}</h3>
							<p class="w-full px-18 text-white">{work.workText || ''}</p>
						</div>
					</div>
				</div>
				{/each} 
				{#if portfoyOnView && portfoyOnView.work}

						<div transition:fade={{ duration:400 ,easing:quintInOut}} class="flex w-full  h-screen fixed top-0 left-0 items-center justify-center cursor-pointer"  on:click={handlePortfoyClose}>
							<div class="bg-gray-800 opacity-90 w-full h-full absolute"></div>
							<div class="flex h-full w-full m-0 sm:h-2/3 sm:w-2/3  bg-contain bg-no-repeat bg-center z-10" 
							style="background-image: url('{portfoyOnView && portfoyOnView.work &&  portfoyOnView.work.img || ''}')">
								
							</div>
						
					</div>
				{/if}
			</div>
		</div>
   </div>
</div>


<div>

</div>


<div class="w-full h-156">
	<iframe title="map" src="https://www.google.com/maps/embed?pb=!1m10!1m8!1m3!1d24034.00816978646!2d27.7885961!3d41.1508736!3m2!1i1024!2i768!4f13.1!5e0!3m2!1str!2str!4v1539594890165"
	 frameborder="0" width="100%" height="100%" style="border:0" allowfullscreen=""></iframe>
</div>

<style>
	.cardEmploye {
		@apply h-124 bg-red-500 bg-cover bg-center flex flex-col items-center justify-center relative;
	}
	.cardEmploye > h3 {
		@apply text-2xl font-bold text-gray-200 z-10;
	}
	.cardEmploye > hr {
		@apply border-y-2 border-red-500 pb-1 w-1/4 z-10;
	}
	.cardEmploye > h4 {
		@apply text-2xl font-semibold text-gray-300 z-10;
	}
	.employe-social {
		@apply z-0;
	}
	.employe-social > a  {
		@apply text-gray-50 z-10;
	}
	.employe-cover{
		@apply w-full h-full absolute opacity-40 bg-gray-600 z-10;
	}
	#carousel-cover {
		@apply bg-gray-800 bg-opacity-60; 
	}
	#carousel {
		background-repeat: no-repeat;  
		background-position: 0% 0%;
		background-size: 100% 100%;
		-moz-transition: all .5s;
    	-webkit-transition: all .5s;
    	transition: all .5s;
		
	}
	#carousel:hover {
		background-size: 110% 110%;

	}
	#carousel:hover > #carousel-cover {
		@apply bg-gray-800 opacity-95 ;
	}

	.portfoy-cover {
		@apply h-full w-full absolute top-0 left-0 bg-gray-900 opacity-50 hover:opacity-95 duration-500;
	}

	
</style>