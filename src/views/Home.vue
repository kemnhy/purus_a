<template>
  <div>
    <div class="top_wrap">
      <Event_modal />
      <Header_w />
      <Side_menu />
      <Visual />
    </div>
    <Care_reason />
    <Service />
    <Main_banner />
    <Process />
    <Real_review />
    <Self_care />
    <Best_pro />
    <FAQ />
    <QR_banner />
    <Footer_w />
    <Bottom_btn/>
  </div>
</template>
<script setup>
import Best_pro from "@/components/Best_pro.vue";
import Care_reason from "@/components/Care_reason.vue";
import FAQ from "@/components/FAQ.vue";
import Header_w from "@/components/Header_w.vue";
import Main_banner from "@/components/Main_banner.vue";
import Process from "@/components/Process.vue";
import QR_banner from "@/components/QR_banner.vue";
import Real_review from "@/components/Real_review.vue";
import Self_care from "@/components/Self_care.vue";
import Service from "@/components/Service.vue";
import Side_menu from "@/components/Side_menu.vue";
import Visual from "@/components/Visual.vue";
import Footer_w from "@/components/Footer_w.vue";
import Bottom_btn from "@/components/Bottom_btn.vue";
import Event_modal from "@/components/Event_modal.vue";
</script>
<style lang="scss" scoped>
.top_wrap {
  overflow: hidden;
  width: 100%;
  height: 100dvh;
  position: relative;
}
</style>
