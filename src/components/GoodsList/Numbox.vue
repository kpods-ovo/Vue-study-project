<template>
    <div class="numbox_content">
        <div class="mui-numbox" data-numbox-min='1' data-numbox-max='maxValue'>
            <button class="mui-btn mui-btn-numbox-minus" type="button">-</button>
            <input id="test" class="mui-input-numbox" type="number" value="1" @change="newNumber($event)" />
            <button class="mui-btn mui-btn-numbox-plus" type="button">+</button>
        </div>
    </div>
</template>

<script>
    import mui from '../../lib/mui/js/mui.js';
    export default {
        name: "numbox",
        data() {
            return {

            }
        },
        methods: {
            newNumber(event){
                this.$store.state.newQuantity = parseInt(event.currentTarget.value);
            }
        },
        props: ['maxValue'],
        watch: {
            maxValue(newValue, oldValue) {
                mui(".mui-numbox").numbox().setOption('max', newValue)
            }
        }
    }
</script>

<style>
    .numbox_content {
        display: inline-block;
    }
</style>