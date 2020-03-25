<template>
    <div class="listsitms clearfix" :title="sitm.title" :title-img="sitm.img" :data-uid="sitm.id">
        <span><img :src="sitm.img" alt=""></span>
        <span>{{sitm.title}}</span>
        <div class="removeline fr" @click="removethis(sitm)">关闭</div> 
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
        removethis:function(sitm){
            this.$emit('removethis',sitm);
        }
       
    }
}
</script>