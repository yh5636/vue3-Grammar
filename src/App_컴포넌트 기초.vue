<template>
    <!-- 
        컴포넌트 
        - 장점 : 재활용
        - 부모-자식간 데이터통신
          : App.vue에서 적용한 color값(데이터)을 MyBtn.vue로 보내 적용
        - props를 활용
          : 해당하는 컴포넌트에 마치 html의 속성처럼 붙어있거나 연결되어있을 경우
            컴포넌트 내부에서 처리하기 위함.
        - <slot>태그 활용
    -->
    
    <!-- <MyBtn text="Banana"/> -->     <!-- Mybtn.vue의 {{ text }} -->
    <MyBtn>Banana</MyBtn>   <!-- Mybtn.vue의 <slot> -->
    <MyBtn 
        :color="color">
        <span style="color: red;">Banana</span> <!-- Mybtn.vue의 <slot> -->
    </MyBtn>  <!-- 데이터값을 넘길때 -->
    <MyBtn 
        large 
        color="royalblue">
        Apple   <!-- Mybtn.vue의 <slot> -->
    </MyBtn> <!-- 문자값 넘길때 -->
    <MyBtn>Cherry</MyBtn>
    <button>Banana</button>
</template>

<script>
import MyBtn from '~/components/MyBtn'

export default {
    components: {
        MyBtn
    },
    data() {
        return {
            color: '#000'
        }
    }
}
</script>