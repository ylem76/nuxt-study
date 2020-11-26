<template>
    <div>
        <h1>dynamic routing</h1>
        <input type="text" v-model="dynamicRoute" />
        <nuxt-link to=""></nuxt-link>
        <button @click="goToDynamic">확인</button>
    </div>
</template>
<script>
export default {
    data() {
        return {
            dynamicRoute: ""
        };
    },
    methods: {
        goToDynamic() {
            this.$router.push("/links/dynamic/" + this.dynamicRoute);
        }
    }
};
</script>
