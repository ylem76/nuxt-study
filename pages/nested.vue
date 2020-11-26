<template>
    <div>
        <h1>nested routing</h1>
        <input type="text" v-model="nestedRoute">
        <button @click="onLoadUser">확인</button>
				<!-- 내용을 나오게 하고 싶은 부분에 nuxt-child 태그를 추가한다. -->
        <nuxt-child />
    </div>
</template>
<script>
export default {
    data() {
      return {
        nestedRoute:''
      }
    },
    methods: {
        onLoadUser() {
            this.$router.push('/nested/' + this.nestedRoute);
        }
    }
}
</script>