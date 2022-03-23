<template>
    <div class="counter">
        <div>{{ counter }}</div>
        <button @click="counter++">Increase</button>
        <input type="text" v-model="someText" />
    </div>
</template>

<script>
export default {
    name: "App",
    data() {
        return {
            counter: 0,
            someText: "",
        };
    },
    watch: {
        counter(newValue, oldValue) {
            console.log(`Old Value: ${oldValue}`);
            console.log(`New Value: ${newValue}`);
        },
        someText() {
            this.updateCounter();
        },
    },

    methods: {
        updateCounter() {
            this.counter++;
            console.log("update");
        },
    },
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;

    color: #2c3e50;
    margin-top: 60px;
}
</style>
