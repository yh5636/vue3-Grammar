컴포넌트 - props, context
 - setup()에서는 this를 참조할 수 없기 때문에 
   매개변수로 props, context를 활용
   : setup(props, context) 순서대로 작성
   : 변수값 접근시 '$'표기X

<template>
    <div
        v-bind="$attrs"
        class="btn"
        @click="hello">
        <slot></slot>    
    </div>
</template>

<script>
import { onMounted } from 'vue'

export default {
    inheritAttrs: false,
    props: {
        color: {
            type: String,
            default: 'gray'
        }
    },
    emits: ['hello'],
    
    // mounted() {
    //     console.log(this.color)
    //     console.log(this.$attrs)
    // },
    
    // methods: {
    //     hello() {
    //         this.$emit('hello')
    //     }
    // },

    // setup() 에서는 this를 참조할 수 없음.
    // 데이터에 직접 접근해야함. 변수값 접근시 '$'표기X
    setup(props, context) {
        function hello() {
            context.emit('hello')
        }
        
        onMounted(()=> {
            console.log(props.color)
            console.log(context.attrs)      //$attrs(X)
        })

        return {
            hello
        }
    }
}
</script>