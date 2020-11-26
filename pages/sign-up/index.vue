<template>
  <div>
    <form action="">
      <input type="text" id="sample3_postcode" placeholder="우편번호" />
      <button @click.prevent="searchAddress = true">우편번호 찾기</button>
      <input type="text" id="sample3_address" placeholder="주소" /><br />
      <input type="text" id="sample3_detailAddress" placeholder="상세주소" />
      <input type="text" id="sample3_extraAddress" placeholder="참고항목" />
    </form>
    <address-popup
      v-show="searchAddress"
      v-bind:searchOpen="searchAddress"
      v-on:close="searchAddress = false"
    >
    </address-popup>
  </div>
</template>
<script>
export default {
  props: ["searchOpen"],
  head: {
    script: [
      {
        src:
          "https://t1.daumcdn.net/mapjsapi/bundle/postcode/prod/postcode.v2.js"
      }
    ]
  },
  data() {
    return {
      searchAddress: false
    };
  },
  methods: {
    closeModal() {
      this.searchAddress = false;
    }
  }
};
</script>
<style></style>
