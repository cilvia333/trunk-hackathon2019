<template lang="pug">
div
  .loading
    .loading-wrapper
      .loading-imgs
        img.loading-img.loading-img-1(src="~/assets/imgs/loading.svg")
        img.loading-img.loading-img-2(src="~/assets/imgs/loading.svg")
        img.loading-img.loading-img-3(src="~/assets/imgs/loading.svg")
      .loading-text: span(v-for="letter in loading") {{letter}}
    transition
      .logo(v-if = "logo")
        img.logo-img(src="~/assets/imgs/cotch.svg")
</template>

<script>
import Logo from "~/components/Logo.vue"
export default {
  components: {
    Logo
  },
  data(){
    return{
      loading:"Loading...",
      logo:true
    }
  },
  mounted(){
    setTimeout(() => {
      this.logo = false
    }, 1000);
  }
}
</script>

<style lang="scss" scoped>
@import "~/assets/style/variables.scss";
@import "~/assets/style/mixin.scss";

.loading{
  display: block;
  width: 100vw;
  height: 100vh;
  background: $theme-orange;
  background: $theme-gradient;
  opacity: 1;
}
.loading-wrapper{
  position:absolute;
  display: block;
  top:0;
  left:0;
  bottom:0;
  right:0;
  margin:auto;
  width: min-content;
  height: min-content;
  opacity: 1;
}
.loading-imgs {
  position: relative;
  display: block;
  margin-left: -26px;
  width: auto;
  height: 160px;
  .loading-img {
    position: absolute;
    width: auto;
    height: 160px;
    top: 0;
    left: 0;
    transform-origin: 55% 100%;
  }
  .loading-img-1 {
    animation: loading 1.6s .0s $bezier-ease-in forwards infinite;
    opacity: 1;
  }
  .loading-img-2 {
    animation: loading 1.6s .1s $bezier-ease-in forwards infinite;
    opacity: 0.5;
  }
  .loading-img-3 {
    animation: loading 1.6s .2s $bezier-ease-in forwards infinite;
    opacity: 0.2;
  }
}
.loading-text{
  display: inline-block;
  padding-top: 16px;
  @include noto-font(3rem);
  white-space: nowrap;
  color:$white;
  span{
    display: inline-block;
    vertical-align: middle;
  }
  span:nth-of-type(1){ animation: loading_text 2s ease 0s infinite;}
  span:nth-of-type(2){ animation: loading_text 2s ease 0.1s infinite;}
  span:nth-of-type(3){ animation: loading_text 2s ease 0.2s infinite;}
  span:nth-of-type(4){ animation: loading_text 2s ease 0.3s infinite;}
  span:nth-of-type(5){ animation: loading_text 2s ease 0.4s infinite;}
  span:nth-of-type(6){ animation: loading_text 2s ease 0.5s infinite;}
  span:nth-of-type(7){ animation: loading_text 2s ease 0.6s infinite;}
  span:nth-of-type(8){ animation: loading_text 2s ease 0.7s infinite;}
  span:nth-of-type(9){ animation: loading_text 2s ease 0.8s infinite;}
  span:nth-of-type(10){ animation: loading_text 2s ease 0.9s infinite;}
}
@keyframes loading {
  0%  { transform: rotateZ(0deg); }
  90% { transform: rotateZ(82deg); }
  100%{ transform: rotateZ(82deg); }
}
@keyframes loading_text {
  0% { margin-top: 0; }
  5% { margin-top: -1em; }
  10% { margin-top: 0; }
  13% { margin-top: -0.5em; }
  16% { margin-top: 0; }
  18% { margin-top: -0.2em; }
  20% { margin-top: 0; }
}

.logo {
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: #fff;
  .logo-img {
    position: absolute;
    margin: auto;
    display: block;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    width: 160px;
    height: auto;
  }
}


</style>
