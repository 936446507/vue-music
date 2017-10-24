<template>
    <div class="tab">
        <router-link v-for="tab in tabList" :key="tab.linkTo"
            tag="div" class="tab-item" :to="tab.linkTo">
            <span class="tab-link">{{tab.value}}</span>
        </router-link>
    </div>
</template>

<script>
export default {
    data() {
        return {
            tabList: [
                {
                    value: '推荐',
                    linkTo: '/recommend',
                },
                {
                    value: '歌手',
                    linkTo: '/singer',
                },
                {
                    value: '排行',
                    linkTo: '/rank',
                },
                {
                    value: '搜索',
                    linkTo: '/search',
                }
            ]
        }
    }
}
</script>

<style lang="stylus" scoped>
@import "~common/stylus/variable"

.tab
    display: flex
    height: 44px
    line-height: 44px
    font-size: $font-size-medium
    .tab-item
        flex: 1
        text-align: center
        .tab-link
            padding-bottom: 5px
            color: $color-text-l
        &.router-link-active
            .tab-link
                color: $color-theme
                border-bottom: 2px solid $color-theme
</style>
