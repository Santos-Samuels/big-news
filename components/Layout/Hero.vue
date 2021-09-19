<template>
    <div>
        <header class="h-48 md:h-56 lg:h-64 w-full text-gray-100">
            <nav class="py-2 px-5 md:px-8 flex items-center justify-between text-xl">
                <div class="flex flex-row flex-nowrap items-center">
                    <i class="bi bi-card-text mr-2"></i>
                    <span><nuxt-link tag="a" to="/">Big News</nuxt-link></span>
                </div>
                
                <ul class="flex flex-nowrap space-x-4">
                    <li><nuxt-link tag="a" to="/">Home</nuxt-link></li>
                    <li><nuxt-link tag="a" to="/blog">Blog</nuxt-link></li>
                </ul>
            </nav>

            <div class="mt-10">
                <h1 class="text-4xl font-bold tracking-widest uppercase text-center"> {{ title }} </h1>
            </div>
        </header>
    </div>
</template>

<script>
export default {
    props: {
        title: { type: String }
    }
}
</script>

<style scoped>
header {
    background-image: url(https://images.pexels.com/photos/167684/pexels-photo-167684.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940);
    background-position: center;
    background-size: cover;
}

nav {
    background-color: #362c478e;
}
</style>