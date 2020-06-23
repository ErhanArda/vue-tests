<template>
    <button @click="$emit('my-custom-event',infoTest)">Click me!</button>
</template>

<script>
export default {
    data: ()=>{
        return {
            info: {id:123,title:'Cool!'},
            field: 'hello'
        }
    },
    computed: {
        infoTest:function(){
            return  { 
                    id:123,
                    title:'Cool!',
                    field: this.field
                }
        }
    }
    
}
</script>