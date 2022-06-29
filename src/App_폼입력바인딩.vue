<template>
    <!-- 
        폼 입력 바인딩 
        - 단방향 데이터 바인딩 : data에 선언된 데이터를 끌고오는 것에서 끝남을 말함.
        - @input 적용으로 사용자의 입력값에 따른 반응성을 가진 데이터로 사용가능(양방향 데이터바인딩)
    -->
    <h1>{{ msg }}</h1>
    <input 
        type="text" 
        v-model="msg" />
    <h1> {{ checked }}</h1>
    <!-- 
        v-model 
        - 주의: 한글 입력시 한박자씩 늦게 갱신됨. 
                따라서 한글의 경우는 @input 활용하는게 좋음.
    -->
    <input 
        type="checkbox" 
        v-model="checked" />
    <!-- 아래는 한글입력시 사용
    :value="msg" 
    @input="msg = $event.target.value"/> 
    -->
    <!-- @input="handler"/> -->
</template>

<script>
export default {
    data() {
        return {
            msg: 'Hello world!',
            checked: false
        }
    }

    // methods: {
    //     handler(event) {
    //         console.log(event.target.value)
    //         this.msg = event.target.value
    //     }
    // }
}
</script>