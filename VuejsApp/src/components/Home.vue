<template>
    <div class="home">
        <h1>{{ msg }}</h1>
        <p>Welcome to your new single-page application, built with <a href="https://vuejs.org" target="_blank">Vue.js</a>.</p>
        <button v-on:click="GetData">GetData</button>
    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        name: 'Home',
        props: {
            msg: String
        },
        methods: {
            GetData() {
                alert('Hello World');
                axios.get('https://localhost:44319/api/values')
                    .then(response => {
                        console.log(response)
                        this.setState({ ideas: response.data })
                    })
                    .catch(error => console.log(error))
            }
        }
    };

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
