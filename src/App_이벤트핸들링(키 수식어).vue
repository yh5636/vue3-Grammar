<template>
    <!-- 
        키수식어 
        - vue.js에서 제공하는 키수식어로 개발시에는 
          반드시 이벤트를 케밥케이스로 바꿔서 적용!!
        - 체이닝으로 적용 가능
    -->
    <input 
    type="text"
    @keydown.ctrl.shift.a="handler" />
    <!-- @keydown.enter="handler" /> -->

</template>

<script>
export default {
    methods: {
        handler(event) {
            // if(event.key === 'Enter') {
                console.log('Enter!!')
            // }
        }
    }
}
</script>