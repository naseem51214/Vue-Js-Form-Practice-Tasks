<template>
    <h1>
        Form Validation in Vue js
    </h1>

    <div>
        <ul>
            <li v-for="item in error" v-bind:key="item">
                {{ item }} not valid
            </li>
        </ul>
    </div>

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
                <label for="">Select Contry: </label>
                <select v-model="form.contry">

                    <option>
                        Pakistan
                    </option>
                    <option>
                        Uk
                    </option>
                    <option>
                        USA
                    </option>
                </select>
            </div>
            <div>
                <h3>technology</h3>

                <label for="">Vue Js</label>
                <input type="checkbox" value="Vue Js" v-model="form.technology">
                <br> <br>
                <label for="">Nuxt Js</label>
                <input type="checkbox" value="Nuxt Js" v-model="form.technology">
                <br> <br>
                <label for="">Next Js</label>
                <input type="checkbox" value="Next Js" v-model="form.technology">
                <br> <br>

            </div>
            <div>
                <h3>
                    Gender
                </h3>
                <label for="">Male</label>
                <input type="radio" value="male" name="gender" v-model="form.gender">
                <br>
                <br>
                <label for="">Female</label>
                <input type="radio" value="Female" name="gender" v-model="form.gender">
            </div>
            <div>
                <button type="button" v-on:click="login">Submit</button>
            </div>
        </div>

    </form>
</template>
<script>
export default {
    name: 'SimpleForm',
    data() {
        return {
            form: {
                email: '',
                password: '',
                contry: '',
                technology: [],
                gender: '',
            },
            error: [],
        }
    },
    methods: {
        login() {


            this.error = []
            for (const item in this.form) {
                if (this.form[item] === "" || this.form[item].length === 0) {
                    this.error.push(item)
                }
            }
            if (this.error.length === 0) {
                alert("Your for has been submited sucessfuly\n" +
                    "Email: " + this.form.email + "\n" +
                    "Contry: " + this.form.contry + "\n" +
                    "Technologies: " + this.form.technology + "\n" +
                    "Gender: " + this.form.gender)
            }
            console.warn(this.form, this.error)
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
    margin-top: 10px;
}

div div select {
    width: 130px;
    margin-left: 10px;
    margin-top: 10px;
}
</style>