Provide, Inject
최상위 부모 컴포 = 상위/조상 컴포넌트
조상 -> 자식 컴포로 데이터 내려줄때 
  : props 활용. 단, 바로 아래의 자식컴포에게만 내려줌.
  : 조상컴포에서 하위 후손 컴포에게 단계를 거치지 않고 
    한번에 데이터를 내려주기 위함.
<template>
    <!-- 
        Provide, Inject 
        - message를 뿌림에 있어
          App > Parent > Child 순서로 한단계씩 내려줌.
        - 이 과정에서 Parent는 단순히 Child에 전달하기 위해 
          사용하지 않는 script를 작성해야함
          -> 이 부분 개선하기위해 나온 개념, 
             즉 Parent라는 매개체 없이 바로 App데이터를 Child에서 사용
        - 주의 
          : 기본적으로 Provide는 반응성을 제공하지 않음! 
            -> 데이터를 전달해서 한번 출력하는 용도로 사용
            -> computed 활용하여 반응성을 주는 것 가능
    -->

    <!-- Provide는 반응성없음 테스트(computed 적용 유무에 따름) -->
    <button @click="message = 'Good?'">
        Click!
    </button>
    <h1>App: {{ message }}</h1>
    <Parent />  <!-- provide를 사용함으로써 불필요하게 된 :msg="message" 삭제 -->

    <!-- <Parent :msg="message" /> -->
</template>

<script>
import Parent from '~/components/Parent'
import { computed } from 'vue' //Provide에 반응성을 주기 위함

export default {
    components: {
        Parent
    },
    data() {
        return {
            message: 'Hello world!'
        }
    },
    provide() {
        return {
            // Provide에 반응성을 주기 위함
            // computed함수 활용하여 콜백으로 원하는 값 도출  
            msg: computed(() => this.message)
            //data()에 선언한 message를 msg로 사용하겠다.
            // msg: this.message 
        }
    }
}
</script>