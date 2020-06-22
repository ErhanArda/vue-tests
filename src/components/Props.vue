<template>
    <div>
        <h1>Advanced Props</h1>
        <div>{{post.title}}</div>
    </div>
</template>
<script>
export default {
    props:{
        title: String,
        isPublished: Boolean,
        views:Number,
        post:Object
    }
}
</script>

<style scoped>

</style>