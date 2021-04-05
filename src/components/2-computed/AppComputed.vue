<template>
    <div class="content-container">
        <sub class="component-title">Computed:</sub>
        <h2>{{ primeiroNome }} tem {{ pegaIdade }} anos!</h2>
    </div>
</template>

<script>
import { reactive, computed } from "vue";

export default {
    name: "AppComputed",

    setup() {
        const user = reactive({
            nome: "Matheus Alves Pereira",
            time: "DEV - ATD",
            dataNascimento: "20/04/1996"
        });

        const primeiroNome = computed(() => user.nome.split(" ")[0]);

        const pegaIdade = computed(() => {
            const dataLista = user.dataNascimento.split("/");
            const idade = new Date().getFullYear() - Number(dataLista[2]);
            return idade;
        });

        return {
            user,
            primeiroNome,
            pegaIdade
        };
    },
};
</script>
