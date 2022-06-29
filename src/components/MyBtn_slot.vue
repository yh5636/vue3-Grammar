<template>
    <!-- 
        slot 
        - Fallback(대체) Contents 
          : MyBtn컴포를 사용하는 App.vue에 지정된 content(Banana)가 없을 경우
            slot에 있는 Apple이 보여짐 

        - 이름을 갖는 slot 
          : 보장된 순서로 노출하고 싶을 때 사용 (순서는 자식컴포 따라감.)
    -->
    <div class="btn">
        <!-- 이름을 갖는 slot -->
        <slot name="icon"></slot>
        <slot name="text"></slot>
        <!-- <slot>Apple</slot> -->
    </div>
</template>

<script>
export default {
    
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