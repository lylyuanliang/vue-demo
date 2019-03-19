<template>
    <div class="login">
        <input v-model="loginInfo.account" placeholder="account"/>
        <input v-model="loginInfo.password" placeholder="password" type="password"/>
        <button id="login-button" v-on:click="login">登陆</button>
        <template v-if="resultShow">{{loginResult}}</template>
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
              },
              loginResult: "",
              resultShow: false
          }
        },
      methods: {
          login() {
              var param = this.loginInfo;
              if(!param.account) {
                alert("input account must!");
                return ;
              }
              if(!param.password) {
                alert("必须输入秘密！");
                return ;
              }
              var url = "/user/login";
              this.axios.get(url, {
                params: param
              })
                .then( (data) => {

                    this.loginResult = data.data.result;
                    this.resultShow = true;
                  //注：使用$set赋值，否则页面不进行渲染
                  // this.$set(this.loginResult, data.data.result);
                  // this.$set(this.resultShow, true);
                }).catch(function (error) {
                   console.log(error);
              });
          }
      }
    }
</script>

<style scoped>

</style>
