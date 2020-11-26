<template>
    <div id="page-wrapper">
        <!--템플릿 html 안에 link로 삽입하기-->
        <link rel="stylesheet" type="text/css" href="/css/style.css" />
        <h1>adding css</h1>
    </div>
</template>
<!--템플릿 바깥쪽에 style로 불러오기-->
<style src="static/css/style.css" scoped></style>

<script>
export default {
    //script 안에서 head 프로퍼티 이용하기
    head: {
        link: [{ rel: "stylesheet", href: "/css/style.css" }]
    },
    mounted() {
        document.body.innerHTML = "<p>makeText!</p>";
    }
};
</script>

<style>
p {
    color: red;
}
</style>
