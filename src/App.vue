<template>
    <div class="header-container">
        <img alt="Vue logo" src="./assets/logo.png" />

        <select
            name="selectComponent"
            id="selectComponent"
            v-model="selectedComponent"
        >
            <option
                v-for="(component, index) in componentsNames"
                :key="index"
                :value="component"
            >
                {{ getComponents[index] }}
            </option>
        </select>
    </div>

    <keep-alive>
        <component :is="selectedComponent"></component>
    </keep-alive>
</template>

<script>
import { ref, computed } from "vue";

// Components
import AppData from "./components/1-data/AppData.vue";
import AppComputed from "./components/2-computed/AppComputed.vue";
import AppWatch from "./components/3-watch/AppWatch.vue";
import AppMethod from "./components/4-method/AppMethod.vue";
import AppProps from "./components/5-props/AppProps.vue";
import AppEmits from "./components/6-emits/AppEmits.vue";
import AppLifecycle from "./components/7-lifecycle/AppLifecycle.vue";

export default {
    name: "App",

    components: {
        AppData,
        AppComputed,
        AppWatch,
        AppMethod,
        AppProps,
        AppEmits,
        AppLifecycle
    },

    setup() {
        const selectedComponent = ref("AppData");
        const componentsNames = [
            "AppData",
            "AppComputed",
            "AppWatch",
            "AppMethod",
            "AppProps",
            "AppEmits",
            "AppLifecycle"
        ];

        const getComponents = computed(() => componentsNames.map(component => component.slice(3)));

        return {
            selectedComponent,
            componentsNames,
            getComponents
        };
    },

};
</script>

<style lang="scss">
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;

    display: grid;
    grid-template-rows: 100px 1fr;
    align-items: center;
    height: 100vh;
}

.header-container {
    display: flex;
    justify-content: center;
    column-gap: 50px;
    img {
        width: 50px;
    }
}

.content-container {
    align-self: flex-start;
    border-radius: 30px;
    padding: 20px 0;
    margin: 10px auto;
    background-color: rgba(158, 158, 158, 0.336);
    width: 80%;
    position: relative;

    .component-title {
        position: absolute;
        left: 20px;
    }
}
</style>
