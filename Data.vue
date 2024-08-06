<template>
    <div>
        <h2>Options - {{ o_firstName }}</h2>
        <h2>Options - {{ o_firstName }} {{ o_lastName }} {{ o_heroName }}</h2>
        
        <h2>Composition - {{ c_firstname }}</h2>
        <h2>Composition - {{ greet }}</h2>

        <hr>

        <h2>Composition - {{ c_firstname }} {{ c_lastname }} {{ c_heroname }}</h2>
        <h2>Composition - {{ greetHero }}</h2>

        <hr>

        <h2>Composition {{ state.firstName }} {{ state.lastName }} {{ state.heroName }}</h2>
        <h2>Composition - {{ reactiveGreetHero }}</h2>

    </div>
</template>

<script>
import { ref, reactive } from 'vue';
    export default {
        name: "Data",
        setup() {
            const c_firstname = ref('Clark')
            const c_lastname = ref('Kent')
            const c_heroname = ref('Superman')

            c_firstname.value = 'Diana'
            
            const greet = `Hello ${c_firstname.value}`
            const greetHero = `Hello ${c_firstname.value} ${c_lastname.value} a.k.a ${c_heroname.value}`

            const state = reactive({
                firstName: 'Princess',
                lastName: 'Diana',
                heroName: 'Wonder Woman'
            })

            const reactiveGreetHero = `Hello ${state.firstName} ${state.lastName} a.k.a ${state.heroName}`
            return {
                c_firstname,
                c_lastname,
                c_heroname,
                greetHero,
                greet,
                reactiveGreetHero,
                state
            }
        },
        
        data() {
            return {
                o_firstName: 'Bruce',
                o_lastName: 'Wayne',
                o_heroName: 'Batman'
            }
        },
    }
</script>

<style scoped>

</style>