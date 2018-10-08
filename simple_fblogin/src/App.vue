<template>
  <div id="app">
    <button @click="login">FBLogin</button>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      
    }
  },
  mounted() {
    window.fbAsyncInit = function() {
      FB.init({
        appId      : '195107717852548',
        cookie     : true,
        xfbml      : true,
        version    : 'v3.1'
      });
      FB.AppEvents.logPageView();
      // FB.getLoginStatus( response => {
      //   console.log('res', response)        // 這裡可以得到 fb 回傳的結果
      // });
    };
  },
  methods:{
    login(){
      let vm = this;
      FB.login((res) =>{
        console.log('response',res)
      },
      {
        scope: 'email, public_profile',
        return_scopes: true
      });
    },
  },
}
</script>

