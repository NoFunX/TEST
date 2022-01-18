<template>
    <div class="wrapper">
        <Toolbar/>

        <div class="content">
            
        </div>
    </div>
</template>

<script>
    import Toolbar from '@/components/Toolbar.vue'

    export default {
        components: {
            Toolbar
        }
        
    }
</script>

<style lang="scss" scoped>
    .wrapper {
        font-family: 'PT Sans', sans-serif;
        font-size: 14px;
        padding: 89px 100px;
        max-width: 1200px;
        width: 100%;
        margin: 0 auto;
        background:  #F7F6F4;
    }
</style>