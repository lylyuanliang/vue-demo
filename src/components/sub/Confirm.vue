<template>
  <div class="confirm-button">
    <button @click="getButtonClick">{{text||"sure"}}</button>
  </div>
</template>

<script>
    export default {
        name: "Confirm",
        props: ["text"],//父组件传给子组件的值
        data () {
            return {
                msg: true
            };
        },
        methods: {
            getButtonClick () {
                //点击按钮的时候向父组件传值
                this.$emit("message", this.msg);
            }
        }
    }
</script>

<style scoped>
  button {
    border: 0;
    color: blue;
  }
</style>
