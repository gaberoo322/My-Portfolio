<template>
  <section class="container min-h-screen flex justify-center items-center text-center mx-auto">
    <div>
      <h1 class="text-black">I am Gabe Greenfield</h1>
      <h3 class="text-black">I like to code the front end</h3>
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
      const numberOfBlades = 800;
      const grass = document.getElementsByClassName('grass')[0];

      function assignRandomStyles(blade) {
        const randomHeight =  Math.floor(Math.random() * 40);
        const randomLeft = Math.floor(Math.random() * (window.innerWidth - 25));
        const randomRotation = Math.floor(Math.random() * 15) - 5;
        blade.style.height = (randomHeight + 60) + 'px';
        blade.style.zIndex = randomHeight;
        blade.style.opacity = randomHeight * 0.12;
        blade.style.left = randomLeft + 'px';
        blade.style.transform = 'rotate(' + randomRotation + 'deg)';
      }

      for (var i = 0; i < numberOfBlades; i++) {
        let blade = document.createElement('div');
        assignRandomStyles(blade);
        grass.appendChild(blade);
      }
    }
  }
}
</script>

<style lang="less">
body {
  color: #fff;
  background: linear-gradient(
  rgba(2, 38, 96, .5),
  rgba(13, 70, 157,.75),
  rgb(109, 84, 169),
  rgb(206, 117, 194),
  rgb(229, 199, 187),
  rgb(219, 144, 125),
  rgb(140, 190, 214),
  rgb(135, 206, 250)
  );
  background-size: 100% 800%;
  -webkit-animation: Gradient 15s ease infinite;
  -moz-animation: Gradient 15s ease infinite;
  animation: Gradient 15s ease infinite;

  .container {
    margin: 0 auto;
    width: 100vw;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }

  .grass {
    position: absolute;
    bottom: 0;
    left: 0;

    > div {
      animation:breeze 8s cubic-bezier(.8,-0.5,.25,1.5) infinite;
      background-color:rgba(0, 99, 0, 0.75);
      border-right:solid 5px rgba(0, 182, 0, 0.75);
      border-top-right-radius:100%;
      bottom:0;
      position:absolute;
      transform-origin:bottom;
      transition:all 100ms ease-in-out;
      width:3px;
    }
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
