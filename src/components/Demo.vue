<template>
  <div class="demo">
    <div class="mi-logo">
      <h4>小米官网logo</h4>
      <div class="logo-box">
        <a href class="logo"></a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Demo',
  data () {
    return {}
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.demo {
  text-align: center;
  .mi-logo {
    .logo-box {
      text-align: left;
      .logo {
        display: inline-block;
        width: 55px;
        height: 55px;
        background: #ff6700;
        position: relative;
      }
      .logo::after,
      .logo::before {
        position: absolute;
        width: 55px;
        height: 55px;
        content: "";
        transition: all 0.2s;
      }
      .logo::before {
        background-image: url("../assets/mi-logo.png");
      }
      .logo::after {
        background-image: url("../assets/mi-home.png");
        margin-left: -55px;
      }
      .logo:hover:before {
        opacity: 0;
      }
      .site-header .logo:hover:after {
        opacity: 1;
      }
      .logo:hover:after,
      .logo:hover:before {
        -webkit-transform: translate3d(55px, 0, 0);
        transform: translate3d(55px, 0, 0);
      }
    }
  }
}
</style>
