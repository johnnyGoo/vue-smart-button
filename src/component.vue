<template>
    <div @touchstart="touchstart" @touchend="touchend" style="user-select: none">
        <div v-show="down" style="position: relative">
            <slot  name="down"></slot>
        </div>
        <div v-show="!down" style="position: relative">
            <slot  name="up"></slot>
        </div>
    </div>
</template>
<style scoped>

</style>

<script>
    // 注册
    export default {
        name: 'vue-smart-button',
        // 声明 props
        props: {},
        data: function () {
            return {down: false}
        },
        methods: {
            touchstart: function () {
                this.down = true
            },
            touchend: function () {
                this.down = false
            }
        },
        mounted: function () {

        }
    }
</script>