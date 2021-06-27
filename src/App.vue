<template>
  <div id="app" class="container flex w-full h-screen">
    <!-- side nav -->
    <!-- <div class="w-1/5 px-8 py-2 border-r border-lighter">
        <button class="w-12 h-12 text-3xl rounded-full hover:bg-lightblue text-blue">
            <i class='bx bxl-twitter'></i>
        </button>
    </div> -->
    <SideNav/>
    <Tweets/>
    <Trending/>
  </div>
</template>

<script>
import SideNav from "./components/SideNav.vue";
import Tweets from "./components/Tweets.vue";
import Trending from "./components/Trending.vue";

export default {
  name: "App",
  components: {
    SideNav,
    Tweets,
    Trending
  },
  data() {
    return {
      
    }
  },
};
</script>


