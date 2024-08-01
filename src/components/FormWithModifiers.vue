<template>
    <h1>
        Form Modifiers in Vue js
    </h1>
    <input type="number" v-model.number="data">
    <h2>
        Data is: {{ typeof(data) }}
    </h2>
</template>

<script>
export default {
    name:'FormWithModifiers',
    data() {
        return {
            data:''
        }
    },
}
</script>