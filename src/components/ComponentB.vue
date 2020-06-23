<template>
    <div>
        {{message}}
        <component-c></component-c>
    </div>
</template>

<script>
import ComponentC from './ComponentC'
import EventBus from '../bus'
export default {
    components:{
        ComponentC
    },
    data: function () {
            EventBus.$on('say-hello', () => {
                this.message = 'Hello from Component A';
            })
            
            return {
                message:'Lonely Component Here!'
            }
        }

}
</script>