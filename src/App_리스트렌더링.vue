<template>
    <button @click="handler">
        Click me!
    </button>
    <ul>
        <!-- 기본 for문 -->
        <li
            v-for="(f, index) in fruits"
            :key="f">
            {{ f }} - {{ index + 1 }}
        </li>
        <br>
        <!-- 객체데이터 활용 -->
        <li
            v-for="fruit in newFruits"
            :key="fruit.id">
            {{ fruit.name }} - {{ fruit.id }}
        </li>
        <br>
        <!-- 객체 구조분해 적용 -->
        <li
            v-for="{ id, name} in newFruits"
            :key="id">
            {{ name }} - {{ id }}
        </li>
    </ul>
</template>

<script>
import shortid from 'shortid'
export default {
    data() {
        return {
            fruits: ['Apple', 'Banana', 'Cherry'],
        }
    },
    computed: {
        newFruits() {
            // defult
            // return this.fruits.map((fruit, index) => {
            //     //객체로 데이터 내보내기
            //     return {
            //         id: index,
            //         name: fruit 
            //     }
            // })

            // shortid 패키지 활용
            return this.fruits.map(fruit => ({
                //객체로 데이터 내보내기
                id: shortid.generate(),
                name: fruit 
            }))
        }
    },
    methods: {
        handler() {
            this.fruits.push('Orange')
        }
    }
}
</script>