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
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
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

  @-webkit-keyframes Gradient {
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

  @-moz-keyframes Gradient {
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
