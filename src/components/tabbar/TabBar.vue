<template>
    <div id="tab-bar">
        <!-- 父组件 里面存放 slot的内容 -->
        <slot></slot>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
    #tab-bar{
        display: flex;
        position: fixed;
        bottom: 0;
        left: 0;
        right: 0;
        background: gray;
    }
</style>