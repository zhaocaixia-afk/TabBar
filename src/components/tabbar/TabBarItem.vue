<template>
    <div class="tab-bar-item">
        <!-- 插槽必然被替换,使用div进行包裹 -->
        <div v-if="!isActive"><slot v-if="!isActive" name="item-icon"></slot></div>
        <div v-else><slot name="item-icon-active"></slot></div>
        <div :class="{active:isActive}">
            <slot name="item-text"></slot>
        </div>    
    </div>
</template>

<script>
    export default {
        name:'TabBarItem',
        data() {
            return {
                isActive: true
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
        .active{
            color: red;
        }
    }
</style>