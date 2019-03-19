<template>
  <div class="first-app">
    {{msg}}
    <!--text为父组件传给子组件的值-->
    <confirm text="祖册" @message="getMessage"></confirm>
    <Login></Login>
    <p>
      <router-link to="/second"> to second page</router-link>
    </p>
  </div>
</template>

<script>
  import Confirm from "./sub/Confirm"
  import Login from "./sub/Login"

  export default {
    name: "First",
    components: {
      Confirm,
      Login
    },
    data() {
      return {
        msg: "my fisrt vue demo1"
      };
    },
    methods: {
        getMessage(val) {
          //val为子组件传给父组件的值
          alert(val);
        }
    }
  };
</script>

<style scoped>
/*scoped 表示样式只在当前组件中生效*/


</style>
