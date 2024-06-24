<template>
    <form class="form">
        <label class="form-label" for="#email">Email:<!-- {{ email }}--></label>
        <input
        v-model="email"
            class="form-input"
            type="email"
            id="email"
            required
            placeholder="Email"
        />
        <label class="form-label" for="#password">Password:<!--{{ password }}--></label>
        <input
        v-model="password"
            class="form-input"
            type="password"
            id="password"
            placeholder="Password"
        />
        <input class="form-submit" type="submit" value="Login" @click="onsubmit"/> 

            <p v-for="user in users" :key="user.id" class="msg">
                {{user.email}} - {{ user.pass }}
            </p>

    </form>
</template>

<script>
import userData from '../assets/login.json'
export default {
  data: () => ({
    email: "",
    password: "",
    users: userData,
  }),

  methods: {

    Login() {
        console.log(this.email);
        console.log(this.users);

        for (let i = 0; i < this.users.length; i++) {   
            if (this.email === this.users[i].email && this.password === this.users[i].pass) {     
                console.log("Login Successful");
                alert("Login Successful");
                return true;
                }else{
                    console.log("Login Failed");
                    alert("Login Failed");
                }
        }
    },

    onsubmit(){
        this.Login();
    }
  },
};
</script>

<style scoped>
/*
.login {
  padding: 2rem;
}
.title {
  text-align: center;
}
.form {
  margin: 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 100%;
  min-width: 350px;
  max-width: 100%;
  background: rgba(19, 35, 47, 0.9);
  border-radius: 5px;
  padding: 40px;
  box-shadow: 0 4px 10px 4px rgba(0, 0, 0, 0.3);
}
.form-label {
  margin-top: 2rem;
  color: white;
  margin-bottom: 0.5rem;
  &:first-of-type {
    margin-top: 0rem;
  }
}
.form-input {
  padding: 10px 15px;
  background: none;
  background-image: none;
  border: 1px solid white;
  color: white;
  &:focus {
    outline: 0;
    border-color: #1ab188;
  }
}
.form-submit {
  background: #1ab188;
  border: none;
  color: white;
  margin-top: 3rem;
  padding: 1rem 0;
  cursor: pointer;
  transition: background 0.2s;
  &:hover {
    background: #0b9185;
  }
}
.msg {
    color: rgb(104, 8, 8);
    text-align: center;
}
*/
</style>