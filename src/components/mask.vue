<template>
    <div id="mask" @click="fromLogin"></div>
</template>

<script>
    import { mapActions } from 'vuex';
    export default {
      mounted() {
        this.$el.style.height = document.body.scrollHeight + 'px';
      },
      methods: {
        ...mapActions(['disableLogin']),
        fromLogin() {
          // this.islogin = true;
          // // 给父组件传递信息
          // this.$parent.$emit('to-login', { text: this.islogin})  
          this.disableLogin();
        },
      }
    }
</script>

<style scoped>
  #mask {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: #ccc;
    opacity: 0.5;
    filter: alpha(opacity=50);
    z-index: 100;
  }
</style>