<template>
    <div id="id">
        <router-view></router-view>
        <main-tab-bar></main-tab-bar>
    </div>
</template>

<script>
    import MainTabBar from './components/MainTabBar'
    export default{
        name:'App',
        components:{
            MainTabBar
        }
    }
</script>

<style lang="scss">
    @import './assets/css/basic.css';
</style>
