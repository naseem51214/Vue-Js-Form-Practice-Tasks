<template>
    <h1>
        Simple Vue js Form
    </h1>
    <p>
        {{ form.email }}
    </p>
    <p>
        {{ form.password }}
    </p>
    <form action="">
        <div class="container">
            <div class="email">
                <label for="">Email: </label>
                <input type="text" placeholder="example@test.com" v-model="form.email">
            </div>

            <div class="password">
                <label for="">Password: </label>
                <input type="password" v-model="form.password">
            </div>
            <div>
                <button type="button" v-on:click="login">LogIn</button>
            </div>
        </div>

    </form>
</template>
<script>
export default {
    name: 'SimpleForm',
    data() {
        return {
            form:{
                email:'',
                password:'',
            }
        }
    },
    methods:{
         login()
         {
            console.warn(this.form.email)
         }
    }
}
</script>

<style scoped>
.container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 20px;
    margin-left: 50px
}

.email input {
    margin-left: 25px;
}

.password {
    margin-top: 10px;
}

div button {
    margin-left: 190px;
    margin-top: 5px;
}
</style>