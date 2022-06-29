<template>
    <!-- 
        wheel 이벤트 & passive 수식어
        - 스크롤이벤트 발생시 동시에 작동하던 브라우저 작동과 스크립트로직 작동을 분리시켜 
        각각 독립적으로 수행하게 함으로써 사용자 최적화 향상. 
        - 최대 5배 속도가 향상됨(화면의 끊어짐이 줄어들고 부드러워짐.) 
    -->
    <div
        class="parent"
        @wheel.passive="handler">
        <div
            class="child"></div>
    </div>
    
    <!-- 
        self 수식어 
        - 정확하게 parent영역만 클릭했을 때만 메소드 실행
        - child 영역을 클릭해도 parent 이벤트가 발생했는데, 이를 방지.
        -->
    <div
        class="parent"
        @click.self="handlerA">
        <div
            class="child"></div>
    </div>
    <br>
     
    <!-- 
        capture 수식어
        - 이벤트 캡처링(<-> 버블링) : child 클릭> child를 포함하는 parent 이벤트도 발생시킴
            (순서 : A -> B)
        - capture.stop : child 클릭시 A만 발생
    -->
    <div
        class="parent"
        @click.capture.stop="handlerA">
        <div
            class="child"
            @click="handlerB"></div>
    </div>
    
    <br>
    
    <!-- 
        stop 수식어(=stopPropagation)
        - 이벤트 버블링 : child 클릭 > child를 포함하는 parent 이벤트도 발생.(순서 : B->A)
        - 버블링을 방지하기 위함.
    -->
    <div
        class="parent"
        @click="handlerA">
        <div
            class="child"
            @click.stop="handlerB"></div>
    </div>


    <!-- 수식어 적용
        - once : 지정한 메소드를 단 한번만 작동 
        - 수식어를 체이닝으로 적용 가능
    -->
    <!-- <a 
        href="https://naver.com"
        target="_balnk"
        @click.once.prevent="handler"> 
        @click.prevent="handler">
        NAVER
    </a>
     -->
</template>

<script>
export default {

    methods: {
        handler(event) {
            for(let i=0; i<10000; i += 1) {
                console.log(event)
            }
        }
    }
    
    //self 수식어
    // methods: {
    //     handlerA(event) {
    //         console.log(event.target)   //클릭이된 요소
    //         console.log(event.currentTarget)    //클릭된 요소가 실행된 함수의 이벤트에 해당하는 요소
    //         console.log('A')
    //     },
    //     handlerB() {
    //         // event.stopPropagation() //전파막기(버블링방지)
    //         console.log('B')
    //     }
    // }
    
    //stop 수식어
    // methods: {
    //     handlerA() {
    //         console.log('A')
    //     },
    //     handlerB(event) {
    //         // event.stopPropagation() //전파막기(버블링방지)
    //         console.log('B')
    //     }
    // }

    // methods: {
    //     handler() {
    //         //event.preventDefault()  //  태그의 기본기능 미작동 처리
    //         console.log('ABC!')
    //     }
    // }
}
</script>

<style scoped lang="scss">
    .parent {
        width: 200px;
        height: 100px;
        background-color: royalblue;
        margin: 10px;
        padding: 10px;
        overflow: auto; //스크롤바 생성
        .child {
            width: 100px;
            height: 2000px;
            // height: 100px;
            background-color: orange;;
        }
    }

</style>