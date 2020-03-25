<template>
    <div class="listsitms clearfix"  :title="sitm.title" :title-img="sitm.img" :data-uid="sitm.id" @click="moveson">
        <label> <input type="checkbox" class="checkin" :value="sitm.title" v-model="sitm.isChecked"></label>
        <span><img :src="sitm.img" alt=""></span>
        <span>{{sitm.title}}</span>
    </div>
</template>
<script>
export default {
    name:"AddList",
    props:{
        sitm:{
            type:Object,
            default:{}
        },
    },
    
    methods:{
        moveson:function(sitm){
            this.$emit('moveson',sitm);
        }
       
    }
}
</script>