<template>
    <MyBtn
        class="heropy"
        style="color:red"
        color="#ff0000"
        @hello="log">
        Apple
    </MyBtn>
</template>

<script>
import Mybtn from '~/components/MyBtn'

export default {
    components: {
        Mybtn
    },
    methods: {
        log() {
            console.log('Hello world!')
        }
    }
}
</script>