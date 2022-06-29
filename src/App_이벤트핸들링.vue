<template>
    <!-- 인수, 이벤트객체 둘다 필요할 때  -->
    <button @click="handler('hi', $event)">
        Click 1
    </button>     
    <button @click="handler('what', $event)">
        Click 2
    </button>
    <br>
    <!-- 한번의 이벤트에 다수개의 함수 적용 
    이 경우 해당 메소드에 필요한 인수,매개변수가 없더라도 ()를 반드시 작성.
    (()생략에 대한 기능은 vue.js에서 제공함)-->
    <button @click="handlerA(), handlerB()">
        Click me!
    </button>
</template>


<script>
import shortid from 'shortid'
export default {
   
    methods: {
        handlerA() {
            console.log('A')
        },
        handlerB() {
            console.log('B')
        }


        // 인수, 이벤트객체 둘다 필요할 때
        // handler(msg, event) {
        //     console.log(msg)
        //     console.log(event)
        // }


        // handler(event) {
        //     console.log(event)
        //     console.log(event.target)
        //     console.log(event.target.textContent)
        // }
    }
}
</script>