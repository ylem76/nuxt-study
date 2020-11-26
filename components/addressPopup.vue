<template>
  <div class="search-address">
    <div
      id="wrap"
      style="border:1px solid;width:500px;height:300px;margin:5px 0;position:relative"
    >
      <button class="btn--close" @click="$emit('close')">지도 검색 닫기</button>
    </div>
  </div>
</template>
<script>
export default {
  mounted() {
    var element_wrap = document.getElementById("wrap");
    new daum.Postcode({
      oncomplete: function(data) {
        var addr = ""; // 주소 변수
        var extraAddr = ""; // 참고항목 변수

        //사용자가 선택한 주소 타입에 따라 해당 주소 값을 가져온다.
        if (data.userSelectedType === "R") {
          // 사용자가 도로명 주소를 선택했을 경우
          addr = data.roadAddress;
        } else {
          // 사용자가 지번 주소를 선택했을 경우(J)
          addr = data.jibunAddress;
        }

        // 사용자가 선택한 주소가 도로명 타입일때 참고항목을 조합한다.
        if (data.userSelectedType === "R") {
          // 법정동명이 있을 경우 추가한다. (법정리는 제외)
          // 법정동의 경우 마지막 문자가 "동/로/가"로 끝난다.
          if (data.bname !== "" && /[동|로|가]$/g.test(data.bname)) {
            extraAddr += data.bname;
          }
          // 건물명이 있고, 공동주택일 경우 추가한다.
          if (data.buildingName !== "" && data.apartment === "Y") {
            extraAddr +=
              extraAddr !== "" ? ", " + data.buildingName : data.buildingName;
          }
          // 표시할 참고항목이 있을 경우, 괄호까지 추가한 최종 문자열을 만든다.
          if (extraAddr !== "") {
            extraAddr = " (" + extraAddr + ")";
          }
          // 조합된 참고항목을 해당 필드에 넣는다.
          document.getElementById("sample3_extraAddress").value = extraAddr;
        } else {
          document.getElementById("sample3_extraAddress").value = "";
        }

        // 우편번호와 주소 정보를 해당 필드에 넣는다.
        document.getElementById("sample3_postcode").value = data.zonecode;
        document.getElementById("sample3_address").value = addr;
        // 커서를 상세주소 필드로 이동한다.
        document.getElementById("sample3_detailAddress").focus();
      }
    }).embed(element_wrap, {
      autoClose: false
    });
  }
};
</script>
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
}

.btn--close {
  width: 100%;
  height: 40px;
  background-color: black;
  color: #fff;
}
</style>
