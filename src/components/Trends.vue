<script setup>
import Friends from './Friends.vue';

const trending = [
    {top: 'Trending in TX', title: 'Gigi', bottom: 'Trending with: Gigi'},
    {top: 'Music', title: 'We Won', bottom: '135K Tweets'},
    {top: 'Pop', title: 'Blue Ivy', bottom: '40k tweets'},
    {top: 'Trending in US', title: 'Denim Day', bottom: '40k tweets'},
    {top: 'Trending', title: 'When Beyonce', bottom: '25.4k tweets'}
];
</script>

<template>
  <div class="lg:block hidden w-1/3 h-full border-l border-lighter px-4 py-2 lg:px-6 overflow-y-auto relative">
    <input class="pl-12 rounded-full w-full p-2 bg-lighter text-sm mb-4 outline-none" placeholder="Search Twitter" />
    <i class="fas fa-search absolute left-0 top-0 mt-5 ml-12 text-sm text-light"></i>
    <div class="w-full rounded-lg bg-lightest">
      <div class="flex items-center justify-between p-3">
        <p class="text-lg font-bold">Trends for You</p>
        <i class="fas fa-cog text-lg text-blue"></i>
      </div>
      <button v-for="(trend,index) in trending" :key="index" class="w-full flex justify-between hover:bg-lighter p-3 border-t border-lighter">
        <div>
          <p class="text-xs text-left leading-tight text-dark"> {{ trend.top}} </p>
          <p class="font-semibold text-sm text-left leading-tight"> {{ trend.title}} </p>
          <p class="text-left text-sm leading-tight text-dark"> {{ trend.bottom}} </p>
        </div>
        <i class="fas fa-angle-down text-lg text-dark"></i>
      </button>
      <button class="p-3 w-full hover:bg-lighter text-left text-blue border-t border-lighter">
        Show More
      </button>
    </div>
    
    <Friends/>
  </div>
</template>


