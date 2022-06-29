<template>
    
    <Child />  <!-- provide를 사용함으로써 불필요하게 된 :msg="message" 삭제 -->
   <!-- <Child :msg="msg" /> --> 
</template>

<script>
import Child from '~/components/Child'

export default {
    components: {
        Child
    }
    // provide를 사용함으로써 불필요하게 된 :msg="message" 삭제
    // ,
    // props: {
    //     msg: {
    //         type: String,
    //         default: ''
    //     }
    // }    
}
</script>
