<template>
   <div class="w-1/5 px-8 py-2 border-r border-lighter">
        <button class="text-3xl rounded-full h-14 w-14 hover:bg-lightblue text-blue">
            <i class='bx bxl-twitter'></i>
            <!-- <i class="fab fa-twitter"></i> -->
        </button>
        <div>
          <!-- use v-for to render list button -->
          <button v-for="(tab,key) in tabs" :key="key" @click="id = tab.id" class=" `focus:outline-none hover:text-blue flex items-center py-2 px-4 hover:bg-lightblue rounded-full mr-auto mb-3 ${ id === tab.id ? 'text-blue' : ''}`">
            <i :class="`${tab.icon} text-2xl mr-4 text-left`"></i>
            <p class="text-lg font-semibold text-left">{{tab.title}}</p>
          </button>
        </div>
          <button class="w-12 h-12 p-3 font-semibold text-white rounded-full bg-blue focus:outline-none lg:h-auto lg:w-full hover:bg-darkblue">
            <p class="hidden lg:block">Tweet</p>
            <i class="fas fa-plus lg:hidden"></i>
          </button>
          <div class="relative lg:w-full">
        <button @click="dropdown = true" class="flex items-center w-full p-2 rounded-full hover:bg-lightblue focus:outline-none">
          <img src="avarta2.jpg" class="w-10 h-10 border rounded-full border-lighter" />
          <div class="hidden ml-4 lg:block">
            <p class="text-sm font-bold leading-tight"> NhatNguyen </p>
            <p class="text-sm leading-tight"> @qnhat3103 </p>
          </div>
          <i class="hidden ml-auto text-lg lg:block fas fa-angle-down"></i>
        </button>
        <div v-if="dropdown === true" class="absolute bottom-0 left-0 w-64 mb-16 bg-white rounded-lg shadow-md border-lightest">
          <button @click="dropdown = false" class="flex items-center w-full p-2 p-3 hover:bg-lightest focus:outline-none">
            <img src="avarta2.jpg" class="w-10 h-10 border rounded-full border-lighter" />
            <div class="ml-4">
              <p class="text-sm font-bold leading-tight"> NhatNguyen </p>
              <p class="text-sm leading-tight"> @qnhat3103 </p>
            </div>
            <i class="ml-auto fas fa-check test-blue"></i>
          </button>
          <button @click="dropdown = false" class="w-full p-3 text-left border-t hover:bg-lightest border-lighter test-sm focus:outline-none">
            Add an existing account
          </button>
          <button @click="dropdown = false" class="w-full p-3 text-left border-t hover:bg-lightest border-lighter test-sm focus:outline-none">
            Log out @qnhat3103
          </button>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  name: "SideNav",
  data() {
    return {
      tabs:[
        {icon: 'bx bxs-home', title: 'Home', id:'home'},
        {icon: 'fas fa-hashtag', title: 'Explore', id: 'explore'},
        {icon: 'far fa-bell', title: 'Notifications', id: 'notifications'},
        {icon: 'far fa-envelope', title: 'Messages', id: 'messages'},
        {icon: 'far fa-bookmark', title: 'Bookmarks', id: 'bookmarks'},
        {icon: 'fas fa-clipboard-list', title: 'Lists', id: 'lists'},
        {icon: 'far fa-user', title: 'Profile', id: 'profile'},
        {icon: 'fas fa-ellipsis-h', title: 'More', id: 'more'}
      ],
      id: 'home',
      dropdown: false,
     
      
    }
  },
 
  
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
>
