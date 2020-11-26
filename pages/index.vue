<template>
    <div class="container">
        <div>
            <!-- component 불러오기 -->
            <Logo />
            <h1 class="title">
                nuxt-study
            </h1>

            <ul>
                <li>넉스트 폴더 구조 안내</li>
                <li>
                    <nuxt-link to="/links">넉스트 링크 및 라우터</nuxt-link>
                </li>
                <li><nuxt-link to="/adding-css">css 연결하기</nuxt-link></li>
                <li>간단 팝업 컴포넌트 제작</li>
            </ul>
        </div>
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
    font-family: "Quicksand", "Source Sans Pro", -apple-system,
        BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial,
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

ul {
    text-align: left;
}
</style>
