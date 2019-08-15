<template>
    <div class="container col-mt-6 mt-5">
        <h2>Login</h2>
        <br>
        <form @submit.prevent="submit">
            <div class="form-group">
                <label>Email address</label>
                <input v-model.trim="form.email" type="email" class="form-control" placeholder="Enter email" autofocus>
                <small class="form-text text-danger">Show errors here</small>
            </div>
            <div class="form-group">
                <label>Password</label>
                <input v-model.trim="form.password" type="password" class="form-control" placeholder="Password">
                <small class="form-text text-danger">Show errors here</small>
            </div>

            <button type="submit" class="btn btn-primary">Login</button>
            <hr>
            <br/>
            <p>Dont have an account?
                <nuxt-link to="/register">Register</nuxt-link>
            </p>
        </form>
    </div>
</template>

<script>
    export default {
        name: "login",
        data() {
            return {
                form: {
                    email: '',
                    password: ''
                }
            }
        },
        methods: {
            async submit() {
                await this.$auth.loginWith('local', {
                    data: this.form
                })
                this.$router.push('/');
            }
        }

    }
</script>

<style scoped>

</style>
