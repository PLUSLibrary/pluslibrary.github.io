<template>
    <div class="sidebar">
        <div class="top">
            <div class="top-inner">
                Plus Blog
            </div>
        </div>
        <div class="inner">
            <div v-for="item in menu" :key="item.title">
                <router-link :to="item.link[0]">
                    <div class="item" :class="{ 'item-current' : item.link.includes($router.currentRoute.path) }">
                        {{ item.title }}
                    </div>
                </router-link>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Sidebar",
    props: {
        menu: Array,
        isMobile: Boolean,
    },
    watch: {
        $route () {
            this.$forceUpdate();
        }
    },
}
</script>

<style scoped>
.sidebar {
    width: 192px;
    height: 100%;
    background-color: #FCEEF5;
    display: inline-block;
}
.sidebar .top {
    background-color: #FFF;
    padding-bottom: 0px;
}
.sidebar .top .top-inner {
    border-bottom: #F3BAD6 solid 4px;
    height: 64px;
    color: #F3BAD6;
    font-family: "medium";
    font-size: 32px;
    text-align: center;
    line-height: 64px;
}
.sidebar .inner {
    height: calc(100% - 70px);
    border-right: 8px solid #FFF;
    margin-right: 8px;
}
.item {
    color: #E05297;
    font-size: 24px;
    transition: 256ms;
    text-align: center;
    font-family: "medium";
    cursor: pointer;
}
.item:hover {
    background-color: #FFF;
}
.item-current {
    background-color: #FFF;
}
</style>
