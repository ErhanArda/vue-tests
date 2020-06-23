<template>
    <ul>
        <li v-for="(item,key) in items" :key="key">
            <div>
                {{ item }}
            </div>
            <button v-on:click="$emit('remove-item',key)">X</button>
        </li>
        
    </ul>
</template>
<script>
export default {
    props:['items'],
}
</script>
<style>
input {
    padding: 5px 15px;
    border-radius: 15px;
}
button {
    text-transform: uppercase;
    font-size: 14px;
    margin-left: 5px;
    font-weight: bold;
}
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