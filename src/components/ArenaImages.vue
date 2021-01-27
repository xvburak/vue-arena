<template>
  <Waterfall id="arena-images" class="flex flex-wrap justify-center" >
      <WaterfallItem v-for="content in contents" :key="content.id" class="relative w-full lg:w-1/5  md:w-1/4 sm:w-1/3 p-2">
  
          <div v-if="content.class === 'Image'" class="rounded-md">
            <img class="rounded-md w-full" :src="content.image.large.url" alt="">
          </div>
          <div v-else-if="content.class === 'Text'" class="rounded-md  bg-gray-100 p-8  md:p-4 sm:p-2 flex flex-wrap content-center">
            <p class="w-full text-center"> {{content.content}} </p>
          </div>
          <div v-else-if="content.class === 'Link'" class="rounded-md">
            <img class="rounded-md w-full" :src="content.image.large.url" alt="">
          </div>
          <div v-else-if="content.class === 'Media'" class="rounded-md">
            <img class="rounded-md w-full" :src="content.image.large.url" alt="">
          </div>
          <div v-else>
            <p>{{content.class}}</p>
          </div>
          <!-- <p>{{content.title}}</p> -->
      </WaterfallItem>
    </Waterfall>
</template>

<script>
   const Waterfall = require("vue2-waterfall").Waterfall;
   const WaterfallItem = require("vue2-waterfall").WaterfallItem;
    
  export default {
    name: 'arena-images',
    components: {
      Waterfall,
      WaterfallItem
    },
    props: {
      contents: Array,
    },
  }
</script>

<style scoped>
</style>