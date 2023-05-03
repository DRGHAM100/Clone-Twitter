<script setup>
import {ref} from 'vue';
const tabs = [
    {icon: 'fas fa-home', title: 'Home', id:'home'},
    {icon: 'fas fa-hashtag', title: 'Explore', id: 'explore'},
    {icon: 'far fa-bell', title: 'Notifications', id: 'notifications'},
    {icon: 'far fa-envelope', title: 'Messages', id: 'messages'},
    {icon: 'far fa-bookmark', title: 'Bookmarks', id: 'bookmarks'},
    {icon: 'fas fa-clipboard-list', title: 'Lists', id: 'lists'},
    {icon: 'far fa-user', title: 'Profile', id: 'profile'},
    {icon: 'fas fa-ellipsis-h', title: 'More', id: 'more'}
];

const id= ref('home');
const dropdown = ref(false);
</script>

<template>
   <div class="w-1/4 border-r border-lighter px-2 lg:px-6 py-2 flex flex-col justify-between">
    <div>
      <button class="h-12 w-12 hover:bg-lightblue rounded-full text-3xl text-blue">
        <i class="fab fa-twitter"></i>
      </button>
      <div>
        <button @click="id = tab.id"
        v-for="(tab,index) in tabs" :key="index"
        :class="`flex items-center focus:outline-none py-2 px-4 hover:bg-lightblue
         hover:text-blue mb-2 rounded-full mr-auto ${tab.id === id ? 'text-blue' : ''}`">
          <i :class="tab.icon" :id="tab.id" class="text-2xl mr-4 text-left"></i>
          <p class="text-lg font-semibold text-left hidden lg:block">{{ tab.title }}</p>
        </button>
      </div>
      <button class="text-white bg-blue rounded-full font-semibold focus:outline-none w-12 h-12 lg:h-auto lg:w-full p-3 hover:bg-darkblue">
        <p class="hidden lg:block">Tweet</p>
        <i class="fa fa-plus lg:hidden"></i>
      </button>
    </div>
    <div class="w-full relative">
      <button @click="dropdown = true" class="flex items-center w-full hover:bg-lightblue rounded-full p-1 focus:outline-none">
        <img src="profile.jpg" alt="profile" class="w-10 h-10 rounded-full border border-lighter">
        <div class="hidden lg:block ml-4">
          <p class="text-sm font-bold leading-tight"> Drgham Dakhol </p>
          <p class="text-sm leading-tight"> @drgham </p>
        </div>
        <i class="hidden lg:block fas fa-angle-down ml-auto text-lg"></i>
      </button>
      <div v-if="dropdown" class="absolute hidden lg:block bottom-14 w-full right-0 rounded-lg shadow-md border-lightest bg-white ml-8">
        <button @click="dropdown = false" class="flex items-center w-full hover:bg-lightest p-3 focus:outline-none">
          <img src="profile.jpg" alt="profile" class="w-10 h-10 rounded-full border border-lighter">
          <div class="ml-4">
            <p class="text-sm font-bold leading-tight"> Drgham Dakhol </p>
            <p class="text-sm leading-tight"> @drgham </p>
          </div>
          <i class="fas fa-check ml-auto text-blue"></i>
        </button>
        <button @click="dropdown = false" class="w-full text-left hover:bg-lightest border-t border-lighter p-3 test-sm focus:outline-none">
          Add an existing account
        </button>
        <button @click="dropdown = false" class="w-full text-left hover:bg-lightest border-t border-lighter p-3 test-sm focus:outline-none">
            Log out @drgham
        </button>
      </div>
    </div>
  </div>
</template>
