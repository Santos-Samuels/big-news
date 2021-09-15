<template>
    <div>
        <h1> <postContent :post="post"/> </h1>
        {{ post }}
    </div>
</template>

<script>
import postContent from '@/components/postContent.vue'
import axios from 'axios'

export default {
    components: { postContent },

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