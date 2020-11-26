<template>
    <div>
        <h1>links/users/_id.vue</h1>
        <h2>dynamic router : {{ $route.params.id }}</h2>
        <button
            class="button--green"
            @click="goToDynamicMore"
            style="margin-top:30px;"
        >
            more-datail
        </button>
    </div>
</template>
<script>
export default {
    //밸리데이션
    // validate(data) {
    //     return data.params.id == 1;
    // }

    methods: {
        goToDynamicMore() {
            this.$router.push(
                "/links/dynamic/" + this.$route.params.id + "/more-detail"
            );
        }
    }
};
</script>
