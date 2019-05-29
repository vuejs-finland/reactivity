<template>
    <div id="app">
        <div class="boxes wrapper">
            <box-message
                v-for="(obj, index) in options"
                :key="index"
                :title="obj.title"
                :message="obj.message"
                class="box item"
            />
        </div>

        <div class="buttons wrapper">
            <button
                v-for="(obj, index) in options"
                :key="index"
                class="button item"
                @click="modify(index)"
            >
                Select {{ obj.title }}
            </button>
        </div>
    </div>
</template>

<script>
import BoxMessage from './components/BoxMessage.vue';

export default {
    name: 'app',
    components: { BoxMessage },

    data() {
        return {
            options: [
                {
                    title: 'Apple',
                    message: 'Use dongle different',
                },
                {
                    title: 'Microsoft',
                    message: 'Your machine. Our update.',
                },
                {
                    title: 'Default Title',
                    message: 'Default Message',
                },
            ] 
        };
    },

    methods: {
        modify(index) {
            this.options[index].message += ' modified'
            if (index === 2) {
                this.options[index].message = 'Default Message';
            }
        },
    },
}
</script>

<style>
.boxes, .wrapper {
    display: flex;
    justify-content: space-between;
    width: 800px;
    margin: 20px auto;
}

.box, .item {
    width: 200px;
}

.button {
    height: 100px;
    width: 220px;
    border: 4px solid #0F0;
    color: #0F0;
    background: #333;
}
</style>
