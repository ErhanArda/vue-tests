<template>
    <div class="bg-gray-200 w-full h-screen flex flex-col items-center p-4">
        <Card></Card>
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

export default {
    name:'two',
    components:{ Lists,Card },
    data:()=>({
        item:'',
        items: ['item1', 'item2']    }),
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
    .wrapper{
        background: blue;
    }
    
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