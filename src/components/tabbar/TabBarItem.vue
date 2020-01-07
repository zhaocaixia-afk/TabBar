<template>
    <div class="tab-bar-item">
        <!-- <h1>我是tabbar组件</h1> -->
        <slot name="item-icon"></slot>
        <slot name="item-text"></slot>
    </div>
</template>

<script>
    export default {
        
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
    }
</style>