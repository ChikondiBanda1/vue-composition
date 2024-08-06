<template>
    <div>
        <h2>{{ state.firstName }} {{ state.lastName }}</h2>
    </div>
</template>

<script>
import { reactive } from 'vue';
    export default {
        name: 'DemoTwo',
        setup() {
            const state = reactive({
                firstName: 'Bruce',
                lastName: 'Wayne',
            })

            return { 
                firstName: state.firstName,            
                lastName: state.lastName,
            }
        }
    }
</script>

<style scoped>

</style>