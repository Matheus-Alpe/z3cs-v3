<template>
    <div class="content-container">
        <sub class="component-title">Method:</sub>
        <h1>Contador: {{ contador }}</h1>
        <div>
            <button v-on:click="incrementCount">Incrementar</button>
            <button @click="resetCount('reset param', $event)">Resetar</button>
        </div>
    </div>
</template>

<script>
import { ref } from 'vue'

export default {
    name: 'AppMethod',

    setup() {
        const contador = ref(0);

        function incrementCount(event) {
            console.log('increment >', event);
            ++contador.value;
        }

        function resetCount(param, event) {
            console.log(param, '>', event);
            contador.value = 0;
        }

        return {
            contador,
            incrementCount,
            resetCount
        }
    },
}
</script>

<style lang="scss" scoped>
.red {
    background-color: red;
}
</style>
