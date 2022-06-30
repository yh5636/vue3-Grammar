<template>
    <h1 @click="increase">
        {{ count }}
    </h1>
    <h1 @click="changeMessage">
        {{ message }}
    </h1>
</template>

<script>
import { ref, computed, watch, onMounted } from 'vue'

export default {

    // 반응성을 가지는 객체의 데이터는
    // 반드시 .value로 작성해야 함.
    // 중요)created 라이프사이클은 onCreated로 적용X
    // -> setup() 함수도 created() 처럼 컴포넌트 생성 직후에 실행되기 때문에
    //    created로 생성한 것은 setup() 내 어디든 작성할 수 있기에 필요치 않음.

    setup() {
        const count = ref(0)
        const doubleCount = computed(() => {
            return count.value * 2
        })
        function increase() {
            count.value += 1
        }

        const message = ref('Hello World')
        const reversedMessage = computed(() =>{
            return message.value.split('').reverse().join('')
        })
        watch(message, newValue => { 
            console.log(newValue)
        })

        function changeMessgae() {
            message = 'Good?!'
        }
        //라이프사이클 적용
        //created
        console.log(message.value)

        onMounted(() => {
            console.log(count.value)
        })

        return {
            count,
            doubleCount,
            increase,
            message: message,
            reversedMessage,
            changeMessage,
        }
    }
}
</script>