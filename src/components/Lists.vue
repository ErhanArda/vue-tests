<template>
    <ul>
        <li v-for="item in items" :key="item">
            {{ item }}
        </li>
    </ul>
</template>
<script>
export default {
    props:['items'],
}
</script>
<style>

ul {
    margin-top: 15px;
}
li {
    padding: 5px 15px;
    margin-bottom: 5px;
    background: white;
    border-radius: 15px;
    color: #555;
    display: flex;
    justify-content: space-between;
}
</style>