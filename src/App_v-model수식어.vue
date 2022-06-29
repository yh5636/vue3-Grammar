<template>
    <!-- 
        v-model.lazy(=@change) 
        - 값을 입력후 엔터키, 탭키, input박스에서 벗어나는 등
          포커스를 input 밖으로 줄 때 데이터가 갱신됨
          (vs input은 값을 입력할때마다 갱신됨.)
        
        v-model.number
        - 숫자데이터타입 유지
          -> v-model의 경우 숫자지만 string으로 변경되어 입력됨.

        v-model.trim
        - text 맨앞뒤 공백제거
           
    -->
    <h1>{{ msg }}</h1>
    <input 
        type="text"
        v-model.trim="msg" /> 
        <!-- v-model="msg" /> -->
        <!-- v-model.number="msg" /> -->
        <!-- :value="msg" 
        @change="msg = $event.target.value"/>  -->
</template>

<script>
export default {
    data() {
        return {
            msg: 'Hello world!',
            // msg: 123,   
        }
    },
    watch: {
            msg() {
                // console.log(this.msg.trim())
                console.log(this.msg)
            }
        }
}
</script>