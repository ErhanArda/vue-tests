<template>
    <div class="bg-gray-200 w-full h-screen flex flex-col items-center p-4">
        <Card name="Erhan Arda" company="YCP"/>

        <!-- <Props :is-published="false" :views="123" :id="post.id" :title="post.title"/> -->

        <Props :is-published="true" :views="123" v-bind="post"/>

        <div>
            <input
            type="text"
            placeholder="Add an item"
            v-model="item"
        />
        <button :disabled="!item" v-on:click.prevent="addItem">Add</button>
        </div>
        <div>
            <lists :items="items"></lists>
        </div>

    </div>
</template>
<script>
import Lists from './Lists'
import Card from './Card'
import Props from './Props'

export default {
    name:'two',
    components:{ Lists,Card,Props},
    data:()=>({
        item:'',
        items: ['item1', 'item2'],
         post:{
             id:1,
             title:'Post title'
         } 
       }),
       
    methods:{
        addItem: function(){
            this.items.push(this.item)
            // this.items.unshift(this.item)
            this.item=''
        }
    }
}
</script>
<style scoped>
    
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
</style>