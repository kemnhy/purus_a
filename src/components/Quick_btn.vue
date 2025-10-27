<template>
  <!-- quick wrap -->
  <ul class="quickMenu">
    <!-- 고탑 버튼(스크롤 시 노출) -->
    <li>
      <button class="stroke" v-if="show" @click="goTop">
        <img src="/images/goTop.png" alt="goTop" />
      </button>
    </li>
  </ul>
</template>

<script setup>
import { onMounted, ref } from "vue";

// goTop 버튼 활성화
const show = ref(false);
const handleScroll = () => {
  show.value = window.scrollY > 300;
};

// 마운트시 이벤트 등록
onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});
// 탑으로 이동함수
const goTop = () => {
  window.scrollTo({
    top: 0,
    behavior: "smooth",
  });
};
</script>

<style lang="scss" scoped>
@use "../assets/styles/variables" as *;
.quickMenu {
  position: fixed;
  width: 3.7%;
  min-width: 40px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  right: 1%;
  bottom: 11%;
  z-index: 999999;
  li {
    width: 100%;
    button {
      cursor: pointer;
      line-height: 1.1;
      width: 100%;
      border: none;
      display: block;
      text-align: center;
      font-weight: 500;
      font-size: 110%;
      background-color: $point-color;
      aspect-ratio: 1 / 1;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      color: #fff;
      margin-bottom: 5px;
      transition: all 0.1s ease;
      &:hover {
        background-color: transparent;
        border: 2.5px solid $point-color;
        color: $point-color;
        font-weight: bold;
      }
    }
    // 탑버튼 (테두리형)
    .stroke {
      background-color: transparent;
      border: 2.5px solid $point-color;
      transition: all 0.3s ease;
      img {
        width: 35%;
      }
    }
  }
}

// responsive
@media screen and (max-width: 1300px) {
  .quickMenu {
    width: 5%;
  }
}
@media screen and (max-width: 1024px) {
  .quickMenu {
    width: 6%;
    li {
      button {
        font-size: 100%;
      }
    }
  }
}
@media screen and (max-width: 768px) {
  .quickMenu {
    width: 7.5%;
  }
}
@media screen and (max-width: 450px) {
  .quickMenu {
    width: 13%;
  }
}
</style>
