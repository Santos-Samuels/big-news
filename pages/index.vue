<template>
  <div>
    <Hero :title="'BIG NEWS'" />
  
    <!-- <div class="article-container grid grid-cols-1 md:grid-cols-2 gap-x-12 gap-y-12 my-12 mx-5 md:mx-8">
      <PostPreview v-for="post in posts" :key="post.id" :post="post"/>
    </div> -->

    <section class="p-8 py-12 text-gray-900">
      <h1 class="text-3xl font-bold mb-3"><i class="bi bi-card-text mr-2"></i> BIG NEWS</h1>
      <p class="text-2xl">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quibusdam eum, iste doloremque labore itaque autem neque veritatis nobis ipsum ea. Ullam perferendis ex amet, doloribus vel, accusamus magni enim atque commodi corrupti sed. Porro itaque necessitatibus facere vero aut aspernatur.</p>
      <div class="mt-5 flex justify-end">
        <nuxt-link class="blog-link text-2xl py-3 px-5 rounded bg-green-600 hover:bg-green-800 text-gray-100" tag="a" to="/blog">Ver notícias</nuxt-link>
      </div>
    </section>

    <Footer />
  </div>
</template>

<script>
import Hero from '@/components/Layout/Hero.vue'
import Footer from '@/components/Layout/Footer.vue'
import PostPreview from '@/components/PostPreview.vue'
import axios from 'axios'

export default {
  components: { Hero, Footer, PostPreview },
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

<style scoped>
.blog-link {
  transition: all 0.3s;
}
</style>