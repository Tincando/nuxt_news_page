<template>
	<div>
		<header
  class="flex items-center justify-center h-screen mb-5 bg-fixed bg-center bg-cover custom-img"
>
  
<img src="https://kotbuzh8.directus.app/assets/382557ec-1dda-4784-a331-570b841dd4c2" class="rounded-lg w-50"/>
	</header>
		<div class="m-0 my-14 ">
			
			<div class="max-w-screen-lg sm:text-center sm:mx-auto mb-10">
				
				<h2 class=" font-sans text-5xl font-bold tracking-tight text-gray-900 base:text-4xl sm:leading-none mb-10">FIGHTING FOR FREEDOM SINCE 2011</h2>
				<p class="text-base text-gray-700 text-2xl mb-20">Over 1000 Long Format Interviews with the <b> MOST IMPORTANT VOICES </b>in the <br/> World.We Provide Access to the <b>TRUTH</b>, Celebrating Different Views, Perspectives and Insights As Well As Promoting Financial Freedom Through DeFi.
<b>Transform Yourself with Real News.</b></p>
				<button class=" h-10 px-5 rounded-full transition-colors duration-150 bg-yellow-500 text-2xl text-white hover:bg-yellow-700 ">Suscribe <b>free</b></button>
				
			</div>
			<div class="flex flex-col space-y-10 ">
			<div class="md:container md:mx-auto md:hover:scale-105  "  v-for="post in posts" key="id" >
			<NuxtLink :to="`/news/${post.id}`">
				<div class="test container shadow-lg" :style="{ backgroundImage: `url(https://kotbuzh8.directus.app/assets/${post.cover_image})` }" >
					<!-- <img class="max-w-full object-center"  :src="`https://kotbuzh8.directus.app/assets/${post.cover_image}`"/>
					-->	
					<div class="content container ">
					<h3 class=" text-4xl  text-white">{{post.title}}</h3>
						<h2 class="text-left pt-40 pl-5 text-4xl text-white font-semibold">CLICK HERE <b> TO FIND OUT</b> MORE</h2>
						<img class="logo w-40 pl-5 pt-5 float-right" src="https://kotbuzh8.directus.app/assets/382557ec-1dda-4784-a331-570b841dd4c2"  /> 
						</div>
			</div>
			</NuxtLink>
			</div>
			</div>
		</div>
	</div>
</template>

<style scoped>

	.custom-img{
		background-image: url("assets\nasa-1lfI7wkGWZ4-unsplash.jpg");
	}
	.test{
		min-height: 500px;
		background-repeat: no-repeat;
		background-position: center;
		background-size: cover;
	}

	.content{
		position: relative;
	}

	.content h3{
		padding-top:30px ;
		padding-left: 20px;
	}

	.logo{
		 border-radius: 50%;
	}

	

</style>

<script setup>
const { getItems } = useDirectusItems();

const posts = await getItems({ collection: "news" });


</script>
