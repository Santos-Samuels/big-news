<template>
    <h1> {{ post.id + " - " + post.title }} </h1>
</template>

<script>
export default {
    props: { 
        post: { type: Object, required: true},
    }
}
</script>