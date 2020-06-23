<template>
    <div class="bg-gray-200 w-full h-screen flex flex-col items-center p-4">
        <Card name="Erhan Arda" company="YCP"/>

        <!-- <Props :is-published="false" :views="123" :id="post.id" :title="post.title"/> -->

        <Props :is-published="true" :views="123" v-bind="post"/>

        <div id="app" v-on:keyup.esc="globalPage = false" v-if="globalPage">
            <!-- Example 1 - using javascript expression -->
            <!-- When the button is clicked, it should increase exampleOne by 12 -->
            <button v-on:click="exampleOne += 12">Example 1</button>
            <div>{{ exampleOne }}</div>
            
            <!-- Example 2 - using a method -->
            <!-- When the button is clicked, it should increase exampleTwo by 2 -->
            <button v-on:click="addTwo" >Example 2</button>
            <div>{{ exampleTwo }}</div>
            
            <!-- Example 3 - using a method with data -->
            <!-- When the button is clicked, it should set exampleThree to data being passed in -->
            <button v-on:click="setV('hello')">Example 3</button>
            <div>{{ exampleThree }}</div>
            
            <!-- Example 4 - using a method -->
            <!-- When the word "Show" is double clicked (dbclick), it should make the text appear! -->
            <button v-on:dblclick="appear">Show</button>
            <div v-if="show">Abracadabra</div>
            
            <!-- Example 5 - using a method -->
            <!-- When the key esc is pressed, the whole page should disappear -->
            
        </div>
        <div>
            <my-button v-on:my-custom-event="handleMyButton" ></my-button>
                    <div v-if="data">
                        {{ data.id }}  {{ data.field }}
                    </div>
        </div>
        <div>
            <input
            type="text"
            placeholder="Add an item"
            v-model="item"
        />
        <button :disabled="!item" v-on:click.prevent="addItem">Add</button>
        </div>
        <div>
            <lists :items="items" v-on:remove-item ="removeItem"></lists>
        </div>

    </div>
</template>
<script>
import Lists from './Lists'
import Card from './Card'
import Props from './Props'
import MyButton from './Button'

export default {
    name:'two',
    components:{ Lists,Card,Props,MyButton},
    data:()=>({
        item:'',
        exampleOne: 0,
        exampleTwo: 0,
        exampleThree:'',
        show:false,
        globalPage: true,
        data:'',
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
        },
        addTwo: function(){
            this.exampleTwo +=2
        },
        setV: function(value){
            this.exampleThree = value
        },
        appear: function(){
            this.show = true
        },
        removeItem: function(itemKey){
            this.items.splice(itemKey,1)
            console.log("remove")
        },
        handleMyButton: function(data){
            this.data = data
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