<template>
    <div class="content-container">
        <sub class="component-title">Data:</sub>
        <h1>Nome: {{ user.nome }}</h1>
        <h2>Time: {{ user.time }}</h2>
        <h5>Data Nascimento: {{ user.dataNascimento }}</h5>
    </div>
</template>

<script>
export default {
    name: 'AppData',

    data() {
        return {
            user: {
                nome: 'Matheus Alves Pereira',
                time: 'DEV - ATD',
                dataNascimento: '20/04/1996'
            }
        }
    }
}
</script>
