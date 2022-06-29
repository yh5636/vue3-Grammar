<template>
    <button @click="handler">
        Click me!
    </button>

    <!-- template와 div 차이 -->
    <template v-if="isShow">
        <h1>Title</h1>
        <p>Paragraph 1</p>
        <p>Paragraph 2</p>
    </template>
    <div v-if="isShow">
        <h1>Title</h1>
        <p>Paragraph 1</p>
        <p>Paragraph 2</p>
    </div>

    <!-- v-if와 v-show 차이 -->
    <h1 v-if='isShow'>
        Hello?!
    </h1>
    <h1 v-else-if="count > 3">
        Count > 3
    </h1>
    <h1 v-else>
        Good~
    </h1>
    <h1 v-show="isShow">
        Hello?!
    </h1>
</template>

<script>
export default {
    data() {
        return {
            isShow: true,
            count: 0
        }
    },
    methods: {
        handler() {
            this.isShow = !this.isShow
            this.count += 1
        }
    }
}
</script>