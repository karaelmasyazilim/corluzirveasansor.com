


<div class="container container-sm mx-auto bg-white">
	<div class="flex flex-col py-42">
		<h2 class="text-5xl font-extrabold text-center">Müşteri Memnuniyeti</h2>
		<p class="text-4xl font-bold px-12 text-center py-6">
			Hizmet verdiğimiz her müşterimizi memnun etmeyi amaç edinmiş, kaliteden ödün vermeyi mazeret kabul etmeyen bir kuruluşuz
		</p>


		<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4  gap-12 pt-42">
			<div class="flex flex-col items-center ">
				<i class="fas fa-feather-alt fa-10x p-2"></i>
				<h2 class="text-4xl p-6 font-semibold">Güvenli</h2>
				<p class=" text-center font-semibold">
					EN 81 Standartlarına göre üretilmiş ürünlerin montajını bakımını ve takibini gerçekleştiriyoruz
				</p>
			</div>
			<div  class="flex flex-col items-center ">
				<i class="fab fa-accessible-icon fa-10x p-2"></i>
				<h2 class="text-4xl p-6 font-semibold">Erişilebilirlik</h2>
				<p class=" text-center font-semibold">
					Butün kabinlerimizde sesli işikli geri bildirim, Kabartmalı tuş takımları bulunmaktadır
				</p>
			</div>
			<div  class="flex flex-col items-center ">
				<i class="fas fa-archway fa-10x p-2"></i>
				<h2 class="text-4xl p-6 font-semibold">Zarif</h2>
				<p class=" text-center font-semibold">
					Yapınızla bir bütünmüş gibi görünen kapılar. Kullanıcılarına premium kalite malzeme deneyimi yaşatacaktır
				</p>
			</div>
			<div  class="flex flex-col items-center ">
				<i class="fa fa-cog fa-10x" aria-hidden="true"></i>
				<h2 class="text-4xl p-6 font-semibold">Uzun ömürlü</h2>
				<p class=" text-center font-semibold">
					Yüksek malzeme kalitesi, Tecrübeli ustalarımız sayesinde uzun yıllar sorunsuz kullanılabilecek asansörler
				</p>
			</div>
		</div>


		<div class="py-42">
			<h2 class="text-5xl font-extrabold text-center mb-6">Kadromuz</h2>
			<h3 class="text-3xl font-semibold text-center">İşini aşkla yapan ekibimiz</h3>
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



<div class="w-full h-screen bg-fixed bg-cover relative flex flex-col items-center justify-center align-middle" style="background-image: url('/stock_images/bg-2.jpg')">
<div class="w-full h-full absolute top-0 left-0 opacity-30 bg-gray-600 z-0"></div>
<div class="z-10">
 <div class="container container-sm mx-auto text-white text-center flex flex-col align-middle items-center">
	<h3 class="text-4xl font-bold "><span class="text-4xl font-bold text-red-500 inline-block">Kaliteyi</span> iyi işçilik, titiz çalışma, kaliteli malzeme, güzel tasarım ve fonksiyonelliğin mükemmel uyumu ile <span class="text-red-500">sağlıyoruz</span></h3>
	<hr class="border-t-2 border-b-2 pb-1 mt-3 border-red-500 w-1/3">
	<button class="border-4 px-8 py-4 m-3 font-bold border-white rounded outline-none">Daha fazla bilgi</button>
 </div>
</div>
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
</style>