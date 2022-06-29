<template>
    <!-- vue.js는 케밥체, 스크립트는 카멜체 -->
    <MyBtn @click="log" @change-msg="logMsg">
        Banana
    </MyBtn>
</template>

<script>
import MyBtn from '~/components/MyBtn'

export default {
    components: {
        MyBtn
    },
    methods: {
        log(event) {
            console.log('Click!!')
            console.log(event)
        },
        logMsg(msg) {
            console.log(msg)
        }
    }
}
</script>