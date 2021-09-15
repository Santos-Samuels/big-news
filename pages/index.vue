<template>
  <div>
    <Hero />
  
    <div class="article-container grid grid-cols-1 md:grid-cols-2 gap-x-12 gap-y-12 my-12 mx-5 md:mx-8">
      <PostPreview v-for="post in posts" :key="post.id" :post="post" :postUpdateDate="new Date(post.updatedAt)"/>
    </div>
  </div>
</template>

<script>
import Hero from '@/components/Layout/Hero.vue'
import PostPreview from '@/components/PostPreview.vue'
import axios from 'axios'

export default {
  components: { Hero, PostPreview },
  // data() {
  //   return {
  //     posts: [
  //       {
  //         id: 1 ,
  //         thumbnail: 'https://images.pexels.com/photos/4636525/pexels-photo-4636525.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940',
  //         title: 'Lorem ipsum dolor sit',
  //         description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis consequat turpis quis tortor faucibus rhoncus. Donec eget pharetra sem, non aliquam libero.',
  //         publication_date: new Date
  //       },
  //       {
  //         id: 2 ,
  //         thumbnail: 'https://images.pexels.com/photos/4636525/pexels-photo-4636525.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940',
  //         title: 'Lorem ipsum dolor sit',
  //         description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis consequat turpis quis tortor faucibus rhoncus. Donec eget pharetra sem, non aliquam libero.',
  //         publication_date: new Date
  //       },
  //       {
  //         id: 3 ,
  //         thumbnail: 'https://images.pexels.com/photos/4636525/pexels-photo-4636525.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940',
  //         title: 'Lorem ipsum dolor sit',
  //         description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis consequat turpis quis tortor faucibus rhoncus. Donec eget pharetra sem, non aliquam libero.',
  //         publication_date: new Date
  //       }
  //     ]
  //   } 
  // },

  async asyncData() {
    const api = 'https://api.nuxtjs.dev/posts'
    const posts = await axios.get(api).then((response) => {
      return response.data
    }) 
    return { posts }
  }
}
</script>
