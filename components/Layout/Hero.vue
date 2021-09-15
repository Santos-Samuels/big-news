<template>
    <div>
        <header class="h-48 md:h-56 lg:h-64 w-full text-gray-100">
            <nav class="py-2 px-5 md:px-8 flex items-center justify-between text-xl">
                <div class="flex flex-row flex-nowrap items-center">
                    <i class="bi bi-card-text mr-2"></i>
                    <span>Big News</span>
                </div>
                
                <ul class="flex flex-nowrap space-x-4">
                    <li>Home</li>
                    <li>Artigos</li>
                </ul>
            </nav>

            <div class="mt-10">
                <h1 class="text-4xl font-bold tracking-widest uppercase text-center">BIG NEWS</h1>
            </div>
        </header>
    </div>
</template>

<style scoped>
header {
    background-image: url(https://images.pexels.com/photos/1542493/pexels-photo-1542493.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940);
    background-position: center;
    background-size: cover;
}

nav {
    background-color: #362c478e;
}
</style>