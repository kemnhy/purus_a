<template>
  <section v-if="show" class="btn-bg">
    <div class="inner">
      <button @click="goEsti" class="btn">나의 견적 알아보기</button>
    </div>
  </section>
</template>
<script setup>
import { onMounted, ref } from "vue";
import { useRouter } from "vue-router";

const show = ref(false);
const router = useRouter();

const handleScroll = () => {
  show.value = window.scrollY > 300;
};

// 마운트시 이벤트 등록
onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});
const goEsti = ()=>{
    router.push("/estimate")

}
</script>
<style lang="scss" scoped>
.btn-bg {
  width: 100%;
  background-color: #fff;
  padding: 20px;
  position: fixed;
  bottom: 0;
  .inner {
    .btn {
      width: 100%;
      font-weight: bold;
    }
  }
}
</style>
