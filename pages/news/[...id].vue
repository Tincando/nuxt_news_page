<template>
	<div  class="container-lg">
		<div class="container mx-auto ">
			<h1 class="mb-4 font-sans text-5xl font-bold tracking-tight text-gray-900 sm:text-4xl sm:leading-none">{{post.title}}</h1>
			<hr class="w-full my-8 border-gray-300" />
			<div class="metadata ">
		<div class="container-sm  flex justify-start">
			<div class="p-8 ">
			<img class="rounded-full w-20" src="//cdn.cnn.com/cnnnext/dam/assets/171011105543-chris-cillizza-small-11.jpg" pinger-seen="true">
			</div>
			<div>
			<p class="pt-8">Just some guy from the web</p>
			</div>
			</div>
			</div>
		
			<div class="">
  <img  :src="`https://kotbuzh8.directus.app/assets/${post.cover_image}`"  class="object-cover">
</div>
			<p class="text-base text-gray-700 md:text-lg sm:px-4">{{post.content}}</p>
		</div>
	</div>
</template>

<script setup>



const { getItemById } = useDirectusItems();
const route = useRoute();

const post = await getItemById({ collection: "news", id: route.params.id });
if (!post) throwError("No article found, 404");
</script>
