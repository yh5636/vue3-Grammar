<template>
    <!-- vue.js는 케밥체, 스크립트는 카멜체 -->
    <MyBtn>
        <!-- 
            이름을 갖는 slot (v-slot: 은 #(약어)로 대체 가능)
            - v-slot을 활용하여 자식컴포에 지정한 name값을 
              부모컴포 template에 지정(<slot name="icon"></slot>)
            - 보장된 순서로 노출하고 싶을 때 사용 (순서는 자식컴포 따라감.)
        -->
        <template #text>
            <span>Banana</span>
        </template>
        <template v-slot:icon>
            <span>(B)</span>
        </template>
        
        <!-- Banana -->
    </MyBtn>
</template>

<script>
import MyBtn from '~/components/MyBtn'

export default {
    components: {
        MyBtn
    }
}
</script>