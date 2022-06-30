컴포지션 API
 - setup()
  : 기본적으로 반응성X(데이터 변화에 따른 화면 갱신X )
  : 반응성을 주기 위해 ref 객체를 함수처럼 활용 
    -> ref가 반응성을 가지는 객체를 반환함.

<template>
    <div @click="increase">
        {{ count }}
    </div>
</template>

<script>
import { ref } from 'vue'

export default {
    // data() {
    //     return {
    //         count: 0
    //     }
    // },
    // methods: {
    //     increase() {
    //         this.count += 1
    //     }
    // },

    // 컴포지션 API 적용
    setup() {
        let count = ref(0)
        function increase() {
            // count += 1
            count.value += 1    // ref객체 내 데이터를 활용
        }

        return {
            count,
            increase
        }
    }
}
</script>