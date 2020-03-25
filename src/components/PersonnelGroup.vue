<template>
    <div class="personnel clearfix">
        <div class="personnel_left">
            <p class="lab1">选择</p>
            <div class="dising_group">
                <p> 
                    <label><input type="checkbox" v-model="allcheck.isChecked" @click="selectall(liststim)"></label> 
                    <span @click="ifshow"> <img src="../assets/images/fileicon.jpg" alt=""  > 设计部</span>
                </p>
                <div class="desin_group_list" v-if="seen">
                    <add-list :key="index" v-for="(sitm,index) in liststim" v-bind:sitm="sitm"  @moveson="moveposition(sitm)"></add-list>
                </div>
            </div>
        </div>
        <div class="personnel_right">
            <p class="lab1">已选择</p>
            <div class="personnel_cont">
                <rightAddList :key="index" v-for="(sitm,index) in rightlist" v-bind:sitm="sitm" @removethis="removefat(sitm)"></rightAddList>
            </div>
        </div>
    </div>
</template>
<style>

.lab1{
    font-size: 18px;
    text-align: center;
    line-height: 30px;
    margin-top: 20px;
}
.dselect{
    max-width: 600px;
    margin: 0 auto;
}

.dselect p, .dselect div{
    cursor: pointer;
}

.personnel_left,.personnel_right{
    float: left;
    width: 48%;
    border: 1px solid #DEDEDE;
    border-radius: 4px;
    background: #F4F6F8;
    height: 400px;
    margin-top: 50px;
    overflow-y: auto;

}
.personnel_right{
    float:right;
}

.allperson > p{
    font-size: 16px;;
}
.department_list{
    padding-left: 20px;;
}
.dising_group{
    padding: 20px 40px;
}
.dising_group p{font-size: 16px;line-height: 40px;}
.dising_group p span,.dising_group p label{
    cursor: pointer;
}
.dising_group img{width:30px;height:40px;display:inline-block;vertical-align: middle;} 
.dising_group div{font-size: 14px;padding-left: 20px;}
.listsitms{
    padding:10px 5px;
    vertical-align: middle;
}
.listsitms:hover{
    background:#E7EAEF;;
}
.listsitms span img{
    display: inline-block;
    width: 30px;
    height: 30px;
    border-radius: 50%;
}
.listsitms input[type="checkbox"]{
    width: 15px;
    height: 15px;
    cursor: pointer;
}
</style>

<script>

import AddList from '../components/addlist'
import rightAddList from '../components/rightAddList'
export default {
    name:"PersonnelGroup",
    data(){
        return{
            seen:true,
            allcheck:[{isChecked:false}],
            liststim:[
                {title:"陈淼",img:require("../assets/images/leader.jpg"),isChecked:false,id:"3"},
                {title:"张兵",img:require("../assets/images/leader.jpg"),isChecked:false,id:"4"},
                {title:"吴老师",img:require("../assets/images/leader.jpg"),isChecked:false,id:"5"}
            ],
            rightlist:[],
        }
    },
    components:{
        "AddList":AddList,
        "rightAddList":rightAddList
    },
    methods:{
        ifshow:function(){
            this.seen = !this.seen;
        },
        moveposition:function(sitm){
            let checked = sitm.isChecked
            let id = sitm.id
            sitm.isChecked = !checked

            let list = this.liststim
            let rightlist = this.rightlist
             if(!checked){
                list.forEach(function(itms){
                    if(id == itms.id){
                        rightlist.push(itms)
                        
                    }else{
                        return
                    }
                })    
            }else{
                // console.log(2)
                rightlist.forEach(function(itms,index){
                    let rightId =sitm.id
                    if(id == itms.id){
                        rightlist.splice(index,1)
                    }else{
                        return
                    }
                })  
                if(rightlist == undefined || rightlist.length <= 0){
                this.allcheck.isChecked=false;
                }
            }
        },

        // 右侧点击关闭按钮
        removefat:function(sitm){
            let checked = sitm.isChecked
            let id = sitm.id
            sitm.isChecked = !checked
            var rightlist= this.rightlist
            rightlist.forEach(function(itms,index){
                let rightId =sitm.id
                if(id == itms.id){
                    rightlist.splice(index,1)
                }else{
                    return
                }
            }) 
            // 如果右侧没有数据，全选按钮状态取消
            if(rightlist == undefined || rightlist.length <= 0){
                this.allcheck.isChecked = false;
            }
            
        },
        mounted(){
        this.$nextTick(function(){
           selectall(sitm)
            })
        },   
        // 全选效果
        selectall:function(){
            
               
                this.$nextTick(function(liststim){
                    

                    sitm.isChecked = this.allcheck.isChecked
                    let checked = sitm.isChecked
                    
                    let id = sitm.id
                    
                })
            
            // if(checked){
            //     let listsitm = this.listsitm.find(res => {return res.id == id})
            //     let rightlist = this.rightlist.find(res => {return res.id == id}) 

            //     if(rightlist){
            //         return;
            //     }else{
            //         this.rightlist.push(listsitm)
            //     }
            // }else{
            //     let key = this.rightlist.findIndex(res => {return res.id == id})
            //     this.rightlist.splice(key , 1);
                
            //     }
        }
    },
    
}
</script>