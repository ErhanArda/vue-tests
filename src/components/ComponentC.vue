<template>
    <div>
        C:{{message}}
    </div>
</template>

<script>
import EventBus from '../bus'
export default {
  
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