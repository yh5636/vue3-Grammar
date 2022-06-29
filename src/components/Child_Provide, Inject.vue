<template>
   <div>
        <!-- inject에 작성한 msg 데이터를 가져와 노출 -->
        Child: {{ msg.value }}  <!-- msg로 데이터가 잘 노출되지 않을 경우 -->
        <br>  
        Child: {{ msg }}   
   </div>
</template>

<script>
export default {
    inject: ['msg'] //provide에 작성한 변수 입력
    
    
    // props: {
    //     msg: {
    //         type: String,
    //         default: ''
    //     }
    // }
}
</script>
