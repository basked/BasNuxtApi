<template>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <nuxt-link class="navbar-brand" to="/">BasNuxt</nuxt-link>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav"
                aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
            <ul class="navbar-nav">

                <li class="nav-item active">
                    <nuxt-link class="nav-link" to="/">Home</nuxt-link>
                </li>
                <li class="nav-item">
                    <nuxt-link class="nav-link" to="/posts">Posts</nuxt-link>
                </li>
            </ul>
            <template v-if="!authenticated">
                <ul class="navbar-nav ml-auto">
                    <li class="nav-item">
                        <nuxt-link class="nav-link" to="/login">Login</nuxt-link>
                    </li>
                    <li class="nav-item">
                        <nuxt-link class="nav-link" to="/register">Register</nuxt-link>
                    </li>
                </ul>
            </template>
            <template v-if="authenticated">
                <ul class="navbar-nav ml-auto">
                    <li class="nav-item">
                        <a class="nav-link">{{user.name}}</a>
                    </li>
                    <li class="nav-item">
                        <a @click.prevent="logout" class="nav-link" to="/logout">Logout</a>
                    </li>
                </ul>
            </template>
        </div>
    </nav>
</template>

<script>
    // import {mapGetters} from 'vuex'

    export default {
        name: "Navbar",
        // computed: {
        //     ...mapGetters({
        //         loggedIn: "auth/authenticated"
        //     })
        // }
       methods:{
            logout(){
                this.$auth.logout();
            }
       }
    }
</script>

<style scoped>

</style>
