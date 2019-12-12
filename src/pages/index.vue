<template>
  <div class="container">
    <div>
      <logo />
      <!-- <h1 class="title">
        nuxt-postcss
      </h1>
      <h2 class="subtitle">
        My stunning Nuxt.js project
      </h2>
      <div class="links">
        <a href="https://nuxtjs.org/" target="_blank" class="button--green">
          Documentation
        </a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          class="button--grey"
        >
          GitHub
        </a>
      </div> -->
    </div>
    <Lottie
      :options="defaultOptions"
      :height="400"
      :width="400"
      v-on:animCreated="handleAnimation"
    />
    <Lottie
      :options="lodingOptions"
      :height="400"
      :width="400"
      v-on:animCreated="handleAnimation"
    />
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import Lottie from '~/components/utils/Lottie.vue'
import * as Like from '~/assets/animation/like.json'
import * as Loading from '~/assets/animation/loading.json'

export default {
  components: {
    Logo,
    Lottie
  },
  data() {
    return {
      // データを定義
      defaultOptions: { animationData: Like },
      animationSpeed: 1,
      lodingOptions: { animationData: Loading }
    }
  },
  methods: {
    handleAnimation(anim) {
      this.anim = anim
    }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
