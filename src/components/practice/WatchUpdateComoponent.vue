<template>
    <h1>watch 예제</h1>
    <div>count: {{ count }}</div>
    <button @click="increamentCount">increment count</button>
    <h1>update 예제</h1>
    <div>message :{{ message }}</div>
    <button @click="updateMessage">updateMessage</button>
</template>


<script>
export default {
    data() {
        return {
            count: 0,
            message: "hello java"

        }
    },
    // 특정 변수값의 변경사항을 인지하는 hook 함수
    // count만 변경시키고 싶다면 쓰는데 updated를 써도 되긴함..
    watch: {
        // 인지하고자하는 변수값과 일치되는 함수명을 사용해야 함
        count() {
            alert("count값 변경")
        }
    },
    // dom객체의 변경사항을 인지하는 hook함수
    updated() {
        alert("dom요소 변경")
    },
    methods: {
        increamentCount() {
            this.count++;
        },
        updateMessage() {
            this.message = "hello python"
        }

    }
}
</script>