<template>
    <!-- <h1>{{ reverseMessage() }}</h1>  methods 처리 -->
    <!-- <h1>{{ reversedMessage }}</h1>  computed 처리 -->
    <h1>{{ reversedMessage }}</h1>
    <h1>{{ reversedMessage }}</h1>
    
</template>
<script>
export default {
    data() {
        return {
            msg: 'Hello Computed!'
        }
    },
    computed: {
        reversedMessage() {
            return this.msg.split('').reverse().join('')
        }
    },
    methods: {
        reverseMessage() {
            return this.msg.split('').reverse().join('')
        }
    }
}
</script>