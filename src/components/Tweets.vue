<script setup>
import {ref} from 'vue';
import Tweet from './Tweet.vue';

const tweet= ref('');

const tweets = ref([
    {content: 'It is so nice outside!',time: '15 min',comments: '1,500', retweets: '1000', like: '1,000,007'}
]);

const following = [
    {src: 'andrew.jpg', name: 'Andrew Tate', handle: '@andrewtate', time: '20 min', tweet: 'I know it hurts when you hear my name', comments: '1,000', retweets: '550', like: '1,000,003'},
    {src: 'elon.jpg', name: 'Elon Musk', handle: '@teslaBoy', time: '55 min', tweet: 'Just do something crazy', comments: '2,030', retweets: '50', like: '20,003'},
    {src: 'mbappe.jpg', name: 'Kylian Mbappe', handle: '@kylianmbappe', time: '1.4 hr', tweet: 'An amazing hat-trick!', comments: '100,000', retweets: '1,000,002', like: '5,000,003'},
    {src: 'andrew.jpg', name: 'Andrew Tate', handle: '@andrewtate', time: '1.4 hr', tweet: 'I just hope you still love me after I\'m gone', comments: '100,500', retweets: '1,000,032', like: '5,000,103'}
];

const addNewTweet = () => {
    let newTweet = {
        content: tweet.value,
        time: '1 sec',
        comments: '0',
        retweets: '0',
        like: '0'
    };
    tweets.value.push(newTweet);
    tweet.value = '';
}
</script>

<template>
    <div class="w-full lg:w-1/2 h-full overflow-y-scroll">
        <div class="px-5 py-3 border-b border-lighter flex items-center justify-between">
            <h1 class="text-xl font-bold">Home</h1>
            <i class="far fa-star text-xl text-blue"></i>
        </div>
        <div class="px-5 py-3 border-b-8 border-lighter flex">
            <div class="flex-none">
                <img src="profile.jpg" class="flex-none w-12 h-12 rounded-full border border-lighter"/>
            </div>
            <form @submit.prevent="addNewTweet" class="w-full px-4 relative">
                <textarea v-model="tweet" placeholder="What's happening?" class="mt-3 pb-3 w-full focus:outline-none"/>
                <div class="flex items-center">
                    <i class="text-lg text-blue mr-4 far fa-image cursor-pointer"></i>
                    <i class="text-lg text-blue mr-4 fas fa-film cursor-pointer"></i>
                    <i class="text-lg text-blue mr-4 far fa-chart-bar cursor-pointer"></i>
                    <i class="text-lg text-blue mr-4 far fa-smile cursor-pointer"></i>
                </div>
                <button type="submit" class="h-10 px-4 text-white font-semibold bg-blue hover:bg-darkblue focus:outline-none rounded-full absolute bottom-0 right-0">
                    Tweet
                </button>
            </form>
        </div>
        <div class="flex flex-col-reverse">
            <div v-for="(tweet,index) in tweets" :key="index" class="w-full p-4 border-b hover:bg-lighter flex">
                <Tweet 
                :img-src="`profile.jpg`" 
                :name="`Drgham Dakhol`"
                :handle="`@drgham`"
                :time= "tweet.time"
                :tweet ="tweet.content"
                :comments ="tweet.comments"
                :likes="tweet.like"
                :re-tweets="tweet.retweets"
                />
            </div>
        </div>
        <div v-for="(follow,index) in following" :key="index" class="w-full p-4 border-b hover:bg-lighter flex">
            <Tweet 
            :img-src="follow.src" 
            :name="follow.name"
            :handle="follow.handle"
            :time= "follow.time"
            :tweet ="follow.tweet"
            :comments ="follow.comments"
            :likes="follow.like"
            :re-tweets="follow.retweets"
            />
        </div>
    </div>
</template>


