<template>
     <div class="relative hidden w-1/3 h-full px-6 py-2 overflow-y-scroll border-l md:block border-lighter">
      <input class="w-full p-2 pl-12 mb-4 text-sm border-none rounded-full bg-lighter" placeholder="Search Twitter" />
      <i class="absolute top-0 left-0 mt-5 ml-12 text-sm fas fa-search text-light"></i>
      <div class="w-full rounded-lg bg-lightest">
        <div class="flex items-center justify-between p-3">
          <p class="text-lg font-bold">Trends for You</p>
          <i class="text-lg fas fa-cog text-blue"></i>
        </div>
        <button v-for="(trend,c) in trending" :key="c" class="flex justify-between w-full p-3 border-t hover:bg-lighter border-lighter">
          <div>
            <p class="text-xs leading-tight text-left text-dark"> {{ trend.top}} </p>
            <p class="text-sm font-semibold leading-tight text-left"> {{ trend.title}} </p>
            <p class="text-sm leading-tight text-left text-dark"> {{ trend.bottom}} </p>
          </div>
          <i class="text-lg fas fa-angle-down text-dark"></i>
        </button>
        <button class="w-full p-3 text-left border-t hover:bg-lighter text-blue border-lighter">
          Show More
        </button>
      </div>
      <div class="w-full my-4 rounded-lg bg-lightest">
        <div class="p-3 ">
          <p class="text-lg font-bold">Who to Follow</p>
        </div>
        <button v-for="(friend,n) in friends" :key="n" class="flex w-full p-3 border-t hover:bg-lighter border-lighter">
          <img :src="`${ friend.src }`" class="object-cover w-12 h-12 max-w-full border rounded-full border-lighter" />
          <div class="hidden ml-4 lg:block">
            <p class="text-sm font-bold leading-tight"> {{ friend.name }} </p>
            <p class="text-sm leading-tight"> {{ friend.handle }} </p>
          </div>
          <button class="px-4 py-1 ml-auto text-sm border-2 rounded-full text-blue border-blue">
            Follow
          </button>
        </button>
        <button class="w-full p-3 text-left border-t hover:bg-lighter text-blue border-lighter">
          Show More
        </button>
      </div>
    </div>
</template>

<script>
export default {
   data() {
       return {
        trending: [
        {top: 'Trending in TX', title: 'Gigi', bottom: 'Trending with: Rip Gigi'},
        {top: 'Music', title: 'We Won', bottom: '135K Tweets'},
        {top: 'Pop', title: 'Blue Ivy', bottom: '40k tweets'},
        {top: 'Trending in US', title: 'Denim Day', bottom: '40k tweets'},
        {top: 'Trending', title: 'When Beyonce', bottom: '25.4k tweets'},
      ],
        friends: [
        {src: "https://images.unsplash.com/photo-1496440737103-cd596325d314?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=334&q=80", name: 'Elon Musk', handle: '@teslaBoy'},
        {src: "https://images.unsplash.com/photo-1503185912284-5271ff81b9a8?ixid=MnwxMjA3fDB8MHxzZWFyY2h8M3x8Z2lybHxlbnwwfHwwfHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=60", name: 'Adrian Monk', handle: '@detective:)'},
        {src: "https://images.unsplash.com/photo-1514315384763-ba401779410f?ixid=MnwxMjA3fDB8MHxzZWFyY2h8N3x8Z2lybHxlbnwwfHwwfHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=60", name: 'Kevin Hart', handle: '@miniRock'}
      ],
    }
   },
}
</script>