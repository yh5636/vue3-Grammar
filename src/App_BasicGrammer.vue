 - 기본 문법으로 작성한 App_BasicGrammer.vue와 
   같은 내용을 컴포지션으로 작성한 App_Composion basec.vue와 비교해서 보기

<template>
    <h1 @click="increase">
        {{ count }} / {{ doubleCount }}
    </h1>
    <h1 @click="changeMessage">
        {{ message }} / {{ revursedMessage }}
    </h1>
</template>

<script>
export default {
    data() {
        return {
            count: 0,
            message: 'Hello World!'
        }
    },
    computed: {
        doubleCount() {
            return this.count * 2
        },
        revursedMessage() {
            this.message.split('').reverse().join('')
        }
    },
    watch: {
        message(newValue) {
            console.log(newValue)
        }
    },
    
    //라이프사이클 적용
    created() {
        console.log(this.message)
    },
    mounted() {
        console.log(this.count)
    },
    methods: {
        increase() {
            this.count += 1
        },
        changeMessage() {
            this.message = 'Good?!'
        }
    }
}

</script>