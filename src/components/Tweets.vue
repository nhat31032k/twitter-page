<template>
    <div class="w-full h-full overflow-y-scroll md:w-1/2">
      <div class="flex items-center justify-between px-5 py-3 border-b border-lighter">
        <h1 class="text-xl font-bold">Home</h1>
        <i class="text-xl far fa-star text-blue"></i>
      </div>
      <div class="flex px-5 py-3 border-b-8 border-lighter">
        <div class="flex-none">
          <img src="avarta2.jpg" class="flex-none w-12 h-12 border rounded-full border-lighter"/>
        </div>
        <form v-on:submit.prevent = "addNewTweet" class="relative w-full px-4">
          <textarea v-model="tweet.content" placeholder="What's up?" class="w-full pb-3 mt-3 focus:outline-none"/>
          <div class="flex items-center">
            <i class="mr-4 text-lg text-blue far fa-image"></i>
            <i class="mr-4 text-lg text-blue fas fa-film"></i>
            <i class="mr-4 text-lg text-blue far fa-chart-bar"></i>
            <i class="mr-4 text-lg text-blue far fa-smile"></i>
          </div>
          <button type="submit" class="absolute bottom-0 right-0 h-10 px-4 font-semibold text-white rounded-full bg-blue hover:bg-darkblue focus:outline-none">
            Tweet
          </button>
        </form>
      </div>
      <div class="flex flex-col-reverse">
        <div v-for="(tweet,index) in tweets" :key="index" class="flex w-full p-4 border-b hover:bg-lighter">
          <div class="flex-none mr-4">
            <img src="avarta2.jpg" class="flex-none w-12 h-12 rounded-full"/>
          </div>
          <div class="w-full">
            <div class="flex items-center w-full">
              <p class="font-semibold"> NhatNguyen </p>
              <p class="ml-2 text-sm text-dark"> @qnhat3103 </p>
              <p class="ml-2 text-sm text-dark"> 5 mins </p>
              <i class="ml-auto fas fa-angle-down text-dark"></i>
            </div>
            <p class="py-2">
              {{ tweet.content }}
            </p>
            <div class="flex items-center justify-between w-full">
              <div class="flex items-center text-sm text-dark">
                <i class="mr-3 far fa-comment"></i>
                <p> 0 </p>
              </div>
              <div class="flex items-center text-sm text-dark">
                <i class="mr-3 fas fa-retweet"></i>
                <p> 0 </p>
              </div>
              <div class="flex items-center text-sm text-dark">
                <i class="mr-3 fas fa-heart"></i>
                <p> 1 </p>
              </div>
              <div class="flex items-center text-sm text-dark">
                <i class="mr-3 fas fa-share-square"></i>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div v-for="(follow,t) in following" :key="t" class="flex w-full p-4 border-b hover:bg-lighter">
        <div class="flex-none mr-4">
          <img :src="`${follow.src}`" class="flex-none object-cover w-12 h-12 rounded-full"/>
        </div>
        <div class="w-full">
          <div class="flex items-center w-full">
            <p class="font-semibold"> {{ follow.name }} </p>
            <p class="ml-2 text-sm text-dark"> {{ follow.handle }} </p>
            <p class="ml-2 text-sm text-dark"> {{ follow.time }} </p>
            <i class="ml-auto fas fa-angle-down text-dark"></i>
          </div>
          <p class="py-2">
            {{ follow.tweet }}
          </p>
          <div class="flex items-center justify-between w-full">
            <div class="flex items-center text-sm text-dark">
              <i class="mr-3 far fa-comment"></i>
              <p> {{ follow.comments }} </p>
            </div>
            <div class="flex items-center text-sm text-dark">
              <i class="mr-3 fas fa-retweet"></i>
              <p> {{ follow.retweets }} </p>
            </div>
            <div class="flex items-center text-sm text-dark">
              <i class="mr-3 fas fa-heart"></i>
              <p> {{ follow.like }} </p>
            </div>
            <div class="flex items-center text-sm text-dark">
              <i class="mr-3 fas fa-share-square"></i>
            </div>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
      
      following: [
        {src: "https://images.unsplash.com/flagged/photo-1595514191830-3e96a518989b?ixid=MnwxMjA3fDB8MHx0b3BpYy1mZWVkfDh8dG93SlpGc2twR2d8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=60", name: 'Kevin dene', handle: '@teslaBoy', time: '20 min', tweet: 'Should I just quarantine on mars??', comments: '1,000', retweets: '550', like: '1,000,003'},
        {src: "https://images.unsplash.com/photo-1624289597638-dee343931f01?ixid=MnwxMjA3fDB8MHx0b3BpYy1mZWVkfDMxfHRvd0paRnNrcEdnfHxlbnwwfHx8fA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=60", name: 'Kevin Hart', handle: '@miniRock', time: '55 min', tweet: 'Should me and the rock do another sub-par movie together????', comments: '2,030', retweets: '50', like: '20,003'},
        {src: "https://images.unsplash.com/photo-1613072848413-b62c7148d3f1?ixid=MnwxMjA3fDB8MHx0b3BpYy1mZWVkfDQwfHRvd0paRnNrcEdnfHxlbnwwfHx8fA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=60", name: 'Elon Musk', handle: '@teslaBoy', time: '1.4 hr', tweet: 'Haha just made a flame thrower. Shld I sell them?', comments: '100,000', retweets: '1,000,002', like: '5,000,003'},
        {src: "https://images.unsplash.com/photo-1619701957786-99ee09dfdf65?ixid=MnwxMjA3fDB8MHx0b3BpYy1mZWVkfDU2fHRvd0paRnNrcEdnfHxlbnwwfHx8fA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=60", name: 'Kim Elson', handle: '@teslaBoy', time: '1.4 hr', tweet: 'Just did something crazyyyyyyy', comments: '100,500', retweets: '1,000,032', like: '5,000,103'}
      ],
      tweets: [
        {content: 'It is so interesting!'}
      ],
      tweet: {content: ''}
     }
    },
     methods: {
     addNewTweet () {
      let newTweet = {
        content: this.tweet.content
      };
      this.tweets.push (newTweet)
    }
  },
}
</script>