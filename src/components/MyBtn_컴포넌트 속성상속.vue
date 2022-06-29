<template>
    <!-- 
        - template의 바로 하위 요소(= 최상위 요소, root 요소) 속성 상속 적용
          : 컴포넌트가 사용되는 곳(App.vue > <MyBtn>)에 작성된 속성이 있을경우
            사용된 컴포넌트(MyBtn.vue)의 최상위 요소의 속성에 더해져 적용됨.

          : 단, 컴포넌트(MyBtn.vue)의 최상위 요소가 2개 이상일 경우 
            컴포넌트가 사용되는 곳(App.vue > <MyBtn>)에 작성된 속성이
            컴포넌트의(MyBtn.vue) 최상위 요소들 중 어디에 적용되어야 할지 모름.
            -> 어떠한 최상위 요소에도 적용X
    -->
    <div class="btn">
        <slot></slot>
    </div>


    <!-- 아래와 같이 직접 지정하여 부모속성상속 적용4 가능 -->
    <h1 v-bind="$attrs">aaa</h1>
    <h1 
        :class="$attrs.class"
        :style="$attrs.style">aaa</h1>
    <!-- <div></div> -->
</template>

<script>
export default {
    //최상위 요소가 하나만 있을 때도, 부모요소 상속받지 않게 함.
    inheritAttrs: false,

    //데이터, 인스터스 생성 직후처리
    created() {
        console.log(this.$attrs)
    }
}
</script>

<style scoped>
    .btn {
        display: inline-block;
        margin: 4px;
        padding: 6px 12px;
        border-radius: 4px;
        background-color: gray;
        color: white;
        cursor: pointer;
    }
</style>