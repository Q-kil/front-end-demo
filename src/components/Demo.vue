<template>
  <div class="demo">
    <div class="ball">
      <h4>小球来回运动</h4>
      <p>一个小球从向右匀速移动 200px，然后移动回来，再移动过去，最后停留在 200px 处。</p>
      <div class=ball-box>
        <div></div>
      </div>
    </div>
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
  .ball {
    .ball-box {
      div {
        width: 40px;
        height: 40px;
        border-radius: 50%;
        background: #0ff;
        animation: move 2s linear 3 alternate both;
      }
    }
  }
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
@keyframes move {
  0% {
    transform: translate(0, 0);
  }
  100% {
    transform: translate(200px, 0);
  }
}
</style>
