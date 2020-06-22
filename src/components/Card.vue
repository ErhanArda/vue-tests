<template>
    <div class="card">
            <div class="card-title">Computer Engineer</div>
            <UserCircle :name="name"/>
            <div class="card-name">
                <div class="light-font">ERHAN</div>
                <div>ARDA</div>
            </div>
            <div class="card-company">YCP</div>
        </div>
</template>

<script>
import UserCircle from './UserCircle'

export default {
    data: ()=>{
        return {name:'Erhan Arda'}
    },
    components: {UserCircle}
}
    
</script>
<style scoped>
.card {
    background: rgb(4, 84, 104);
    color: #dff1f5;
    padding: 15px;
    border-radius: 0 0 15px 15px;
    width: 200px;
    height: 200px;
    display: flex;
    flex-direction: column;
    align-items: center;
}
.card-title {
    text-transform: uppercase;
    font-size: 12px;
    font-weight: bold;
    margin-bottom: 10px;
}

.card-name {
    display: flex;
    text-transform: uppercase;
    margin-top: 15px;
}
.light-font {
    color: #7dd2d5;
    margin-right: 5px;
}
.card-company {
    font-size: 14px;
}
</style>