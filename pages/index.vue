<template>
  <section class="container">
    <div>
      <h1 class="text-grey-darker">I am Gabe Greenfield</h1>
      <h3 class="text-grey-darker">I like to code the front end</h3>
      <div class="links">
        <a href="https://www.linkedin.com/in/gabriel-greenfield-91941579/" target="_blank">
          <img class="h-12 w-12" src="/svg/linkedin.svg">
        </a>
        <a href="https://github.com/gaberoo322" target="_blank">
          <img class="h-12 w-12" src="/svg/github.svg">
        </a>
        <a href="https://twitter.com/GabeGreenfield" target="_blank">
          <img class="h-12 w-12" src="/svg/twitter.svg">
        </a>
        <a href="https://www.facebook.com/gabe.greenfield" target="_blank">
          <img class="h-12 w-12" src="/svg/facebook.svg">
        </a>
      </div>
    </div>
    <div class="grass"></div>
  </section>
</template>

<script>
export default {
  mounted() {
      this.growgrass();
  },
  methods: {
    growgrass() {
      var numberOfBlades = 600;
      var grass = document.getElementsByClassName('grass')[0];

      function assignRandomStyles(blade) {
        var randomHeight =  Math.floor(Math.random() * 100);
        var randomLeft = Math.floor(Math.random() * (window.innerWidth - 8));
        var randomRotation = Math.floor(Math.random() * 10) - 5;
        blade.style.height = (randomHeight + 50) + 'px';
        blade.style.zIndex = randomHeight;
        blade.style.opacity = randomHeight * 0.02;
        blade.style.left = randomLeft + 'px';
        blade.style.transform = 'rotate(' + randomRotation + 'deg)';
      }

      for (var i = 0; i < numberOfBlades; i++) {
        var blade = document.createElement('div');
        assignRandomStyles(blade);
        grass.appendChild(blade);
      }
    }
  }
}
</script>

<style lang="less">
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
body {
  width: 100vh;
  height: 90vh;
  color: #fff;
  background: linear-gradient(
    -45deg,
    rgba(99, 193, 50, 1),
    rgba(184, 225, 255, 1),
    rgba(161, 205, 244, 1)
  );
  background-size: 400% 400%;
  -webkit-animation: Gradient 15s ease infinite;
  -moz-animation: Gradient 15s ease infinite;
  animation: Gradient 15s ease infinite;

  .container {
    margin: 0 auto;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }

  .grass > div {
    animation:breeze 8s cubic-bezier(.8,-0.5,.25,1.5) infinite;
    background-color:rgb(0, 146, 0);
    border-right:solid 5px rgb(0, 94, 0);
    border-top-right-radius:100%;
    bottom:0;
    position:absolute;
    transform-origin:bottom;
    transition:all 100ms ease-in-out;
    width:3px;
  }

  @keyframes breeze {
    0%, 100% {
      transform:auto;
    }
    50% {
      transform:rotate(10deg);
    }
  }

  @keyframes Gradient {
    0% {
      background-position: 0% 50%;
    }
    50% {
      background-position: 100% 50%;
    }
    100% {
      background-position: 0% 50%;
    }
  }
}
</style>
