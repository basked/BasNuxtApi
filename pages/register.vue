<template>
    <div class="container col-mt-6 mt-5">
        <h2>Register</h2>
        <br>
        <form>
            <div class="form-group">
                <label>Full Name</label>
                <input type="text" class="form-control" placeholder="Enter you name">
                <small class="form-text text-danger">Show errors here</small>
            </div>
            <div class="form-group">
                <label>Email address</label>
                <input type="email" class="form-control" placeholder="Enter email">
                <small class="form-text text-danger">Show errors here</small>
            </div>
            <div class="form-group">
                <label>Password</label>
                <input type="password" class="form-control" placeholder="Password">
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
        name: "register"
    }
</script>

<style scoped>

</style>
