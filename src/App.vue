<template>
    <Button/>
</template>

<script>
import Button from './components/Button.vue'

export default {
    name: 'App',
    components: {
        Button,
    },
    data() {
        return {
            isModalVisible: false,
        };
    },
    methods: {}
}
</script>

<style>
body {
    background: darkseagreen;
}

button {
    text-align: center;
}
</style>
