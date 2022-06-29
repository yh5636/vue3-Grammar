<template>
    <!-- 
        emit 
        - 부모컴포넌트의 이벤트를 자식컴포넌트에 가져와서 사용가능하게 함.
        - 최상위요소가 2개 이상이거나, 부모속성상속 미적용하도록 되어있어도 
          직접적으로 연결하기때문에 해당 이벤트에 연결되어있는 부모컴포메소드가 실행됨.
        - 부모컴포넌트에 적용된 이벤트명(click)을 자식컴포넌트의 emits: []에 작성후,
          해당이벤트명을 그대로 자식컴포넌트에 작성해주면 됨.
        - 컴포넌트를 사용하는 곳에 연결해서 emits라는 옵션으로 받아서 사용하는 경우 정의만 정확히 해주면
          이벤트명을 click처럼 액션이벤트명이 아니어도 상관없음. aaa로 해도 됨.
        
        ex) 부모컴포 <MyBtn @clickA="log"> 
            -> 자식컴포 emits: ['clickA'] 
            -> 자식컴포 <h1 @click="$emit('clickA')">
    -->
    <div class="btn">
        <slot></slot>
    </div>
    <h1 @dblclick="$emit('click', $event)">ABC</h1>
    <h1 @dblclick="$emit('click', 123)">ABC</h1>
    <h1 @click="$emit('click')">ABC</h1>
    <input 
        type="text" 
        v-model="msg" />
</template>

<script>
export default {
    emits: [
        'click',
        'changeMsg' // @change-msg
    ],
    data() {
        return {
            msg: ''
        }
    },
    watch: {
        msg() {
            // emits에 선언한 changeMsg이벤트(부모컴포 @change-msg)에 적용된 
            // 메소드를 사용할 때
            this.$emit('changeMsg', this.msg)   //$emit('이벤트명', 넘길데이터)  
        }
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