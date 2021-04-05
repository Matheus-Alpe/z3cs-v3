<template>
    <div class="content-container">
        <sub class="component-title">Watch:</sub>
        <form>
            <label for="name">Nome:</label>
            <input id="name" type="text" v-model="user.nome" />
        </form>
        <div>
            <h2>{{ user.nome }}</h2>
            <p>Quantidade de alterações: {{ quantidadeAlteracoes }}</p>
        </div>
    </div>
</template>

<script>
import { reactive, ref, watch } from "vue";

export default {
    name: "AppWatch",

    setup() {
        const user = reactive({
            nome: "Matheus Alves Pereira",
            time: "DEV - ATD",
            dataNascimento: "20/04/1996"
        });

        const quantidadeAlteracoes = ref(0);

        watch(user, () => {
            console.log("<< Atributo do User foi alterado! >>");
            quantidadeAlteracoes.value++;
        });

        watch(quantidadeAlteracoes, (novaQuantidade, antigaQuantidade) => {
            console.log(
                `Novo === ${novaQuantidade}   ||   Antigo === ${antigaQuantidade}`
            );
        });

        return {
            user,
            quantidadeAlteracoes
        };
    }
};
</script>

<style lang="scss" scoped>
input {
    margin-left: 10px;
}
</style>
