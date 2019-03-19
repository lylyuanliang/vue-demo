<template>
    <div class="login">
        <input v-model="loginInfo.account" placeholder="account"/>
        <input v-model="loginInfo.password" placeholder="password" type="password"/>
        <button id="login-button" v-on:click="login">登陆</button>
    </div>
</template>

<script>
    export default {
        name: "login.vue",
        data() {
          return {
              loginInfo: {
                  account: "",
                  password: ""
              }
          }
        },
      methods: {
          login() {
              var param = this.loginInfo;
              var url = "/user/login";
              this.axios.get(url, param)
                .then(function (data) {
                    console.log(data);
                }).catch(function (error) {
                   console.log(error);
              });
          }
      }
    }
</script>

<style scoped>

</style>
