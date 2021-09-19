<template>
    <div>
        <article class="grid grid-cols-1 lg:grid-cols-2">
            <div class="flex flex-row flex-nowrap">
                <div class="article-date mr-4">
                    <p class="text-lg"> {{ new Date(post.updatedAt).toLocaleString('pt-br', { month: 'short' }).slice(0, -1) }} </p>
                    <hr class="w-4 my-2 border-black border-opacity-25">
                    <span class="font-semibold text-3xl"> {{ new Date(post.updatedAt).getDate() }} </span>
                </div>

                <div class="w-full lg:mr-4 ">
                    <img class="article-thumbnail w-full h-56 object-cover" :src="post.image" alt="Post Image">
                </div>
            </div>

            <div class="article-info flex flex-col justify-between w-full mt-3 lg:mt-0">
                <div>
                    <nuxt-link tag="a" :to="'/post/' + post.id" class="article-title font-semibold text-2xl"> {{ post.title }} </nuxt-link>
                    <p class="article-description mt-3"> {{ post.description }} </p>
                </div>

                <div>
                    <hr class="my-3 border-black border-opacity-25">
                    <nuxt-link tag="a" to="#" class="flex justify-end items-center flex-nowrap">
                        <span class="font-semibold mr-1">Leia mais</span>
                        <i class="bi bi-chevron-right text-sm"></i>
                    </nuxt-link>
                </div>
            </div>
        </article>
    </div>
</template>

<script>
export default {
    props: { 
        post: { type: Object, required: true}

    }
}
</script>
