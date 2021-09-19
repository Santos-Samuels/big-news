<template>
    <div>
        <Hero :title="post.title" />

        <section class="flex justify-between my-4 mx-5">
            <nuxt-link v-if="post.id > 1" class="bg-green-200 p-2 rounded hover:bg-green-400" tag="a" :to="'/post/' + (post.id-1)">Previous</nuxt-link>
            <span v-else> </span>
            <nuxt-link v-if="post.id < 7" class="bg-green-200 p-2 rounded hover:bg-green-400" tag="a" :to="'/post/' + (post.id+1)">Next</nuxt-link>
        </section>
        
        <section class="grid grid-cols-1 md:grid-cols-2 border-b md:pb-5">
            <div>
                <img class="w-full h-80 object-cover" :src="post.image" alt="">
            </div>
            <div class="m-3 md:my-0 md:relative">
                <p class="text-2xl lg:text-3xl"> {{ post.description + '.' }} </p>
                
                <div class="flex justify-end md:absolute md:bottom-0 md:right-0">
                    <p class="w-100 text-center mt-3 bg-gray-200 p-2 rounded"> Publicado em: {{ new Date(post.updatedAt).toLocaleDateString('pt-BR') }} </p>
                </div>
            </div>
        </section>

        <section class="m-3 md:m-8 mt-5 post-content">
            <h1 class="font-bold text-2xl">Lorem ipsum dolor sit amet.</h1>
            <p class="mt-2">Lorem ipsum dolor sit amet consectetur adipisicing elit. Deleniti nostrum tenetur tempora voluptatum sunt repudiandae quas in fugit nobis neque asperiores perferendis rerum nam expedita culpa modi dolore dolores odit nihil blanditiis, sint similique, amet illo? Quam, exercitationem. A velit dicta at doloremque iste, perferendis omnis culpa laborum quibusdam corrupti aliquid beatae cupiditate, tempora id quaerat quae ullam quidem unde perspiciatis veniam cumque ea! Eos, eveniet! Deserunt laboriosam deleniti aut debitis ut est ipsum doloribus explicabo. Eaque similique corporis, nostrum ipsa quae quisquam facilis ullam ad maxime, iusto neque inventore pariatur eum, nesciunt voluptatibus nam fuga numquam quidem cumque repellat.</p>
            <p class="mt-5">Lorem ipsum dolor sit amet consectetur adipisicing elit. Soluta libero, illum a ad, architecto cum vel maiores dicta omnis quas exercitationem repellat adipisci neque excepturi modi molestiae. Velit sapiente aspernatur necessitatibus amet soluta! Dolore alias sit, quos, quaerat ab consequuntur nam minus at impedit quia quidem molestias aut, assumenda mollitia dolores laboriosam. Harum consectetur quibusdam sed at delectus dignissimos ipsum, modi fuga sint, eaque hic totam quo dicta non quia? Rerum eveniet repudiandae, molestias totam architecto earum animi, inventore quidem corporis velit aperiam in nesciunt itaque vel excepturi alias sit sapiente obcaecati veritatis voluptatibus omnis quasi eos dolor culpa. Facere aspernatur, eveniet debitis magni fugit porro ex aliquid obcaecati! Nihil odio quidem officiis? Beatae itaque laborum suscipit facilis! Corporis, ad.</p>
        </section>
    </div>
</template>

<script>
import Hero from '@/components/Layout/Hero.vue'
import axios from 'axios'

export default {
    components: { Hero },
    
    data() {
        return {
        } 
    },

    async asyncData(route) {
        const postID = route.params.slug
        const api = `https://api.nuxtjs.dev/posts/${postID}`
        const post = await axios.get(api).then((response) => {
            return response.data
        }) 
        return { post }
    }
}
</script>

<style scoped>
/* .post-content {
    text-indent: 2em;
} */
</style>