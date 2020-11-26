<template>
  <div class="search-address">
    <div id="wrap">
      <p>모달 내용</p>
      <button @click="$emit('close')">모달 닫기</button>
    </div>
  </div>
</template>

<style>
.search-address {
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
}

#wrap {
  position: absolute;
  top: 50px;
  left: 50%;
  transform: translateX(-50%);
  background-color: #fff;
  padding: 50px;
}

.btn--close {
  width: 100%;
  height: 40px;
  background-color: black;
  color: #fff;
}
</style>
