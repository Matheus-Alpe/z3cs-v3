<template>
    <div class="content-container">
        <sub class="component-title">Component: User</sub>
        <h1>Nome: {{ propUser.nome }}</h1>
        <h2>Time: {{ propUser.time }}</h2>
        <h5>Data Nascimento: {{ propUser.dataNascimento }}</h5>
    </div>
</template>

<script>
// import { toRefs } from 'vue'

export default {
    name: 'UserProp',

    //------- props: ['propUser']
    props: {
        propUser: {
            type: Object,
            default() {
                return {
                    nome: 'Default',
                    time: 'Linx',
                    dataNascimento: '01/01/2000'
                }
            },
        }
    },

    setup(props) {
        console.log('toRefs props >', props);
        // const { propUser } = toRefs(props);
        // console.log('propUser >', propUser)
    }
}

/*

    Tipos para checagem:

    -   String
    -   Number
    -   Boolean
    -   Array
    -   Object
    -   Date
    -   Function
    -   Symbol

*/
</script>
