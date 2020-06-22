<template>
    <div>
        <h1>Advanced Props</h1>
        <div>{{id}} {{title}}</div>

        <div>{{isPublished}}</div>
   
    </div>
</template>
<script>
export default {
    props:{
        id:Number,
        title: String,
        isPublished: {
            type:[Boolean,Number],
            default: false
        },
        views:Number,
    }
}
</script>

<style scoped>

</style>