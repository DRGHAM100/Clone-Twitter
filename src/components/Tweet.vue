<script setup>
defineProps({
    imgSrc: String,
    name: String,
    handle: String,
    time: String,
    tweet: String,
    comments: String,
    likes: String,
    reTweets: String
});
</script>

<template>
    <div class="flex-none mr-4">
        <img :src="`${imgSrc}`" class="h-12 w-12 rounded-full flex-none"/>
    </div>
    <div class="w-full">
        <div class="flex items-center w-full">
            <p class="font-semibold"> {{ name }} </p>
            <p class="text-sm text-dark ml-2"> {{ handle }} </p>
            <p class="text-sm text-dark ml-2"> {{ time }} </p>
            <i class="fas fa-angle-down text-dark ml-auto"></i>
        </div>
        <p class="py-2">
            {{ tweet }}
        </p>
        <div class="flex items-center justify-between w-full">
            <div class="flex items-center text-sm text-dark">
                <i class="far fa-comment mr-3"></i>
                <p> {{ comments }} </p>
            </div>
            <div class="flex items-center text-sm text-dark">
                <i class="fas fa-retweet mr-3"></i>
                <p> {{ reTweets }} </p>
            </div>
            <div class="flex items-center text-sm text-dark">
                <i class="fas fa-heart mr-3"></i>
                <p> {{ likes }} </p>
            </div>
            <div class="flex items-center text-sm text-dark">
                <i class="fas fa-share-square mr-3"></i>
            </div>
        </div>
    </div>
</template>

