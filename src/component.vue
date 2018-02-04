<template>
    <div @touchstart="touchstart" @touchend="touchend" style="user-select: none">
        <slot v-if="down" name="down"></slot>
        <slot v-if="!down" name="up"></slot>

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