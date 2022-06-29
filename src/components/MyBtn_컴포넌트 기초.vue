<template>
    <div 
    :class="{ large }"
    :style="{ backgroundColor: color }"
    class="btn">
        <!-- {{ text }} -->
        <slot></slot>
    </div>
    <!-- <div clas="btn"></div> -->
</template>

<script>
export default {
    //css 속성
    //App.vue에서 보내준 color값을 받음.
    props: {
        color: {
            type: String,
            default: 'gray'
        },
        large: {
            type: Boolean,
            default: false
        },
        //<slot>태그 사용시 불필요
        // text: {
        //     type: String,
        //     dafault: ''
        // }

    }
}
</script>

<style scoped lang="scss">
    .btn {
        display: inline-block;
        margin: 4px;
        padding: 6px 12px;
        border-radius: 4px;
        background-color: gray;
        color: white;
        cursor: pointer;
        // scss
        &.large {
        font-size: 20px;
        padding: 10px 20px;
        }
    }
    // //css
    // .btn.large {
    //     font-size: 20px;
    //     padding: 10px 20px;
    // }
</style>