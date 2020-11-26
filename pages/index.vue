<template>
  <div class="container">
    <div>
      <!-- component 불러오기 -->
      <Logo />
      <h1 class="title">
        nuxt-study
      </h1>
      <div class="links">
        <a
          href="/a-link"
          target="_self"
          rel="noopener noreferrer"
          class="button--green"
        >
          a-link
        </a>
        <!-- nuxt router link -->
        <nuxt-link to ="/nuxt-link" class="button--grey">nuxt-link</nuxt-link>
        <button class="button--green" @click="$router.push('/router-push')">router-push</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {

    }
  },

  mothods: {
    routerPush() {
      alert('test');
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
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
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
