<template>
    <div class="container">
        <ul>
            <li>
                <p>a 링크</p>
                <a
                    href="/links/a-link"
                    target="_self"
                    rel="noopener noreferrer"
                    class="button--green"
                >
                    a-link
                </a>
            </li>
            <li>
                <p>넉스트 링크</p>
                <nuxt-link to="/links/nuxt-link" class="button--grey"
                    >nuxt-link</nuxt-link
                >
            </li>
            <li>
                <p>라우터 push</p>
                <button
                    class="button--green"
                    @click="$router.push('/links/router-push')"
                >
                    router-push
                </button>
            </li>
            <li>
                <p>동적라우팅</p>
                <nuxt-link to="/links/dynamic" class="button--green"
                    >dynamic route</nuxt-link
                >
            </li>
            <li>
                <p>중첩라우팅</p>
                <nuxt-link to="/links/nested" class="button--grey"
                    >nested route</nuxt-link
                >
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    data() {
        return {};
    },

    mothods: {
        routerPush() {
            alert("test");
        }
    }
};
</script>
<style scoped>
ul {
    list-style: none;
}

ul li {
    margin-bottom: 30px;
}
a {
    margin: 0 !important;
}
</style>
