<template>
    <div class="hello">
        Open Dev Tools to get what you're looking for!
        <!--    <br>-->
        <!--     {{pokemon}}-->
    </div>

</template>

<script>

    import axios from 'axios'

    export default {
        name: 'HelloWorld',

        // data() {
        //     return {
        //         pokemon: {}
        // //     }
        // },

        created() {
            axios.get('https://reqres.in/api/users/2')
                .then(response => {
                    console.log(response.data)
                    // this.pokemon = response.data
                })
                .catch(err => {
                    console.log(err)
                })

            let data_post = {
                'name': 'Kuttoh',
                'job': 'Intern',
            }

            axios.post('https://reqres.in/api/users', data_post)
                .then(response => {
                    console.log(response)
                    // this.pokemon = response.data
                    // this.otherResponses= [response.status, response.statusText, response.headers, response.config]
                })
                .catch(err => {
                    console.log(err)
                })
        }


    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    h1, h2 {
        font-weight: normal;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }

    li {
        display: inline-block;
        margin: 0 10px;
    }

    a {
        color: #42b983;
    }
</style>
