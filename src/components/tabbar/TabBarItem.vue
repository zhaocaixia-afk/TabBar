<template>
    <div class="tab-bar-item" @click="itemClick">
        <!-- 插槽必然被替换,使用div进行包裹 -->
        <div v-if="!isActive">
            <slot v-if="!isActive" name="item-icon"></slot>
        </div>
        <div v-else>
            <slot name="item-icon-active"></slot>
        </div>
        <div :style="activeStyle">
            <slot name="item-text"></slot>
        </div>    
    </div>
</template>

<script>
    export default {
        name:'TabBarItem',
        data() {
            return {
                // isActive: true
            }
        },
        props:{
            path: String,
            activeColor:{
                type:String,
                default:'red'
            }
        },
        computed: {
            // isActive为图片的 显示与隐藏 关键值
            isActive(){
                // this.path:父组件 传过来的值 
                // this.$route.path:当前路由的值
                return this.$route.path.indexOf(this.path) !== -1
            },
            // 动态 传入值的颜色,默认为红色
            activeStyle(){
                return this.isActive ? { color:this.activeColor} : {}
            }
        },
        methods: {
            itemClick(){
                this.$router.replace(this.path)
            }
        },
    }
</script>

<style lang="scss" scoped>
    .tab-bar-item{
        flex: 1;
        text-align: center;
        height: 49px;
        font-size: 14px;
        img{
            width: 24px;
            height: 24px;
            margin-top: 3px;
            // vertical-align: middle;
            // margin-bottom: 2px;
        }
        // .active{
        //     color: red;
        // }
    }
</style>