<template>
    <div class="content-container">
        <sub class="component-title">Lifecycle:</sub>
        <h1>{{ titulo }}</h1>
        <button @click="alterarTitulo">Alterar titulo</button>
    </div>
</template>

<script>
import {
    onUnmounted,
    ref,
    onBeforeMount,
    onMounted,
    onBeforeUpdate,
    onUpdated,
    onBeforeUnmount,
    onActivated,
    onDeactivated
} from "vue";

export default {
    setup(_, context) {
        const titulo = ref("VueJS");

        function alterarTitulo() {
            titulo.value = "Lifecycles - VueJS";
        }
        function destruirInstancia() {
            console.log(context);
        }


        onActivated(() => {
            console.log(`00.1 - onActivated()`)
        })

        onDeactivated(() => {
            console.log(`00.2 - onDeactivated()`)
        })

        onBeforeMount(() => {
            console.log("01 - onBeforeMount()");
        });

        onMounted(() => {
            console.log("02 - onMounted()");
        });

        onBeforeUpdate(() => {
            console.log("03 - onBeforeUpdate()");
        });

        onUpdated(() => {
            console.log("04 - onUpdated()");
        });

        onBeforeUnmount(() => {
            console.log("05 - onBeforeUnmount()");
        });

        onUnmounted(() => {
            console.log("06 - onUnmounted()");
        });

        return {
            titulo,
            alterarTitulo,
            destruirInstancia
        };
    }

};
</script>
