<template>
    <div class="hello">
        <button :style="style" @mouseover="changeColor" @mouseleave="changeColor" @click="showModal">Click</button>
        <Modal
            v-show="isModalVisible"
            @close="closeModal"
        />
    </div>
</template>

<script>
import Modal from "@/components/Modal";

export default {
    name: 'ButtonButton',
    methods: {
        random(max = 255) {
            return Math.floor(Math.random() * max)
        },

        changeColor() {
            let red = this.random()
            let green = this.random()
            let blue = this.random()
            this.style.backgroundColor = `rgb(${red}, ${green}, ${blue})`
            this.style.color = `rgb(${255 - red}, ${255 - green}, ${255 - blue})`
        },
        showModal() {
            this.isModalVisible = true;
        },
        closeModal() {
            this.isModalVisible = false;
        }

    },
    data() {
        return {
            style: {
                backgroundColor: `rgb(255, 255, 255)`,
                color: `rgb(0, 0, 0)`,
            },
            isModalVisible: false,
        }
    },
    components: {
        Modal
    }
}
</script>

<style scoped>
.hello {
    text-align: center;
    margin-top: 100px;
}

button {
    transform: rotate(0deg) scale(2);
    font-family: Consolas, monospace;
    border-radius: 0;
    cursor: pointer;
    transition: ease all 1s;

}

button:hover {
    border-radius: 10px;
    transition: ease all 1s;
    transform: rotate(360deg) scale(3);
}
</style>
