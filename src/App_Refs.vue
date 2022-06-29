<template>
    <!-- 
        ref : 특정요소를 참조할 수 있게 하는 속성
         - 주의 
           : 생성된 컴포(html)가 브러우저에 연결된 직후에만 사용 가능
             즉, mounted에서만 사용 가능.
    -->

    <!-- 컴포에서 ref 속성 활용 -->
    <Hello ref="hello"/>
    <br>
    <!-- <h1 ref="hello">
        Hello world!
    </h1>
    <br>
    <h1 id="hello">
        Hello world!
    </h1> -->
</template>

<script>
import Hello from '~/components/Hello'

export default {
    components: {
        Hello
    },
    created() {
        // console.log(this.$refs.hello)
    },
    mounted() {
        // this.$refs.hello
        // const h1E1 = document.querySelector('#hello')
        // console.log(this.$refs.hello.textContent)
        // console.log(this.$refs.hello)

        //el: 해당하는 컴포의 최상위 html 요소
        //단, 이 경우 다수개의 최상위요소가 존재하면 못찾음.!!
        // console.log(this.$refs.hello.$el)

        //다수개의 최상위 요소 존재시 
        //ref 지정한 것 호출
        console.log(this.$refs.hello.$refs)
        console.log(this.$refs.hello.$refs.good)
        console.log(this.$refs.hello.$refs.bad)
    }
}
</script>